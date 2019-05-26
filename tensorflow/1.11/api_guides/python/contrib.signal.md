# Signal Processing (contrib)
[TOC]

<a href="../../api_docs/python/tf/contrib/signal.md"><code>tf.contrib.signal</code></a> is a module for signal processing primitives. All
operations have GPU support and are differentiable. This module is especially
helpful for building TensorFlow models that process or generate audio, though
the techniques are useful in many domains.

<h2 id="Framing_variable_length_sequences">Framing variable length sequences</h2>

When dealing with variable length signals (e.g. audio) it is common to "frame"
them into multiple fixed length windows. These windows can overlap if the 'step'
of the frame is less than the frame length. <a href="../../api_docs/python/tf/contrib/signal/frame.md"><code>tf.contrib.signal.frame</code></a> does
exactly this. For example:

```python
# A batch of float32 time-domain signals in the range [-1, 1] with shape
# [batch_size, signal_length]. Both batch_size and signal_length may be unknown.
signals = tf.placeholder(tf.float32, [None, None])

# Compute a [batch_size, ?, 128] tensor of fixed length, overlapping windows
# where each window overlaps the previous by 75% (frame_length - frame_step
# samples of overlap).
frames = tf.contrib.signal.frame(signals, frame_length=128, frame_step=32)
```

The `axis` parameter to <a href="../../api_docs/python/tf/contrib/signal/frame.md"><code>tf.contrib.signal.frame</code></a> allows you to frame tensors
with inner structure (e.g. a spectrogram):

```python
# `magnitude_spectrograms` is a [batch_size, ?, 129] tensor of spectrograms. We
# would like to produce overlapping fixed-size spectrogram patches; for example,
# for use in a situation where a fixed size input is needed.
magnitude_spectrograms = tf.abs(tf.contrib.signal.stft(
    signals, frame_length=256, frame_step=64, fft_length=256))

# `spectrogram_patches` is a [batch_size, ?, 64, 129] tensor containing a
# variable number of [64, 129] spectrogram patches per batch item.
spectrogram_patches = tf.contrib.signal.frame(
    magnitude_spectrograms, frame_length=64, frame_step=16, axis=1)
```

<h2 id="Reconstructing_framed_sequences_and_applying_a_tapering_window">Reconstructing framed sequences and applying a tapering window</h2>

<a href="../../api_docs/python/tf/contrib/signal/overlap_and_add.md"><code>tf.contrib.signal.overlap_and_add</code></a> can be used to reconstruct a signal from a
framed representation. For example, the following code reconstructs the signal
produced in the preceding example:

```python
# Reconstructs `signals` from `frames` produced in the above example. However,
# the magnitude of `reconstructed_signals` will be greater than `signals`.
reconstructed_signals = tf.contrib.signal.overlap_and_add(frames, frame_step=32)
```

Note that because `frame_step` is 25% of `frame_length` in the above example,
the resulting reconstruction will have a greater magnitude than the original
`signals`. To compensate for this, we can use a tapering window function. If the
window function satisfies the Constant Overlap-Add (COLA) property for the given
frame step, then it will recover the original `signals`.

<a href="../../api_docs/python/tf/contrib/signal/hamming_window.md"><code>tf.contrib.signal.hamming_window</code></a> and <a href="../../api_docs/python/tf/contrib/signal/hann_window.md"><code>tf.contrib.signal.hann_window</code></a> both
satisfy the COLA property for a 75% overlap.

```python
frame_length = 128
frame_step = 32
windowed_frames = frames * tf.contrib.signal.hann_window(frame_length)
reconstructed_signals = tf.contrib.signal.overlap_and_add(
    windowed_frames, frame_step)
```

<h2 id="Computing_spectrograms">Computing spectrograms</h2>

A spectrogram is a time-frequency decomposition of a signal that indicates its
frequency content over time. The most common approach to computing spectrograms
is to take the magnitude of the [Short-time Fourier Transform][stft] (STFT),
which <a href="../../api_docs/python/tf/contrib/signal/stft.md"><code>tf.contrib.signal.stft</code></a> can compute as follows:

```python
# A batch of float32 time-domain signals in the range [-1, 1] with shape
# [batch_size, signal_length]. Both batch_size and signal_length may be unknown.
signals = tf.placeholder(tf.float32, [None, None])

# `stfts` is a complex64 Tensor representing the Short-time Fourier Transform of
# each signal in `signals`. Its shape is [batch_size, ?, fft_unique_bins]
# where fft_unique_bins = fft_length // 2 + 1 = 513.
stfts = tf.contrib.signal.stft(signals, frame_length=1024, frame_step=512,
                               fft_length=1024)

# A power spectrogram is the squared magnitude of the complex-valued STFT.
# A float32 Tensor of shape [batch_size, ?, 513].
power_spectrograms = tf.real(stfts * tf.conj(stfts))

# An energy spectrogram is the magnitude of the complex-valued STFT.
# A float32 Tensor of shape [batch_size, ?, 513].
magnitude_spectrograms = tf.abs(stfts)
```

You may use a power spectrogram or a magnitude spectrogram; each has its
advantages. Note that if you apply logarithmic compression, the power
spectrogram and magnitude spectrogram will differ by a factor of 2.

<h2 id="Logarithmic_compression">Logarithmic compression</h2>

It is common practice to apply a compressive nonlinearity such as a logarithm or
power-law compression to spectrograms. This helps to balance the importance of
detail in low and high energy regions of the spectrum, which more closely
matches human auditory sensitivity.

When compressing with a logarithm, it's a good idea to use a stabilizing offset
to avoid high dynamic ranges caused by the singularity at zero.

```python
log_offset = 1e-6
log_magnitude_spectrograms = tf.log(magnitude_spectrograms + log_offset)
```

<h2 id="Computing_log_mel_spectrograms">Computing log-mel spectrograms</h2>

When working with spectral representations of audio, the [mel scale][mel] is a
common reweighting of the frequency dimension, which results in a
lower-dimensional and more perceptually-relevant representation of the audio.

<a href="../../api_docs/python/tf/contrib/signal/linear_to_mel_weight_matrix.md"><code>tf.contrib.signal.linear_to_mel_weight_matrix</code></a> produces a matrix you can use
to convert a spectrogram to the mel scale.

```python
# Warp the linear-scale, magnitude spectrograms into the mel-scale.
num_spectrogram_bins = magnitude_spectrograms.shape[-1].value
lower_edge_hertz, upper_edge_hertz, num_mel_bins = 80.0, 7600.0, 64
linear_to_mel_weight_matrix = tf.contrib.signal.linear_to_mel_weight_matrix(
  num_mel_bins, num_spectrogram_bins, sample_rate, lower_edge_hertz,
  upper_edge_hertz)
mel_spectrograms = tf.tensordot(
  magnitude_spectrograms, linear_to_mel_weight_matrix, 1)
# Note: Shape inference for <a href="../../api_docs/python/tf/tensordot.md"><code>tf.tensordot</code></a> does not currently handle this case.
mel_spectrograms.set_shape(magnitude_spectrograms.shape[:-1].concatenate(
  linear_to_mel_weight_matrix.shape[-1:]))
```

If desired, compress the mel spectrogram magnitudes. For example, you may use
logarithmic compression (as discussed in the previous section).

Order matters! Compressing the spectrogram magnitudes after
reweighting the frequencies is different from reweighting the compressed
spectrogram magnitudes. According to the perceptual justification of the mel
scale, conversion from linear scale entails summing intensity or energy among
adjacent bands, i.e. it should be applied before logarithmic compression. Taking
the weighted sum of log-compressed values amounts to multiplying the
pre-logarithm values, which rarely, if ever, makes sense.

```python
log_offset = 1e-6
log_mel_spectrograms = tf.log(mel_spectrograms + log_offset)
```

<h2 id="Computing_Mel_Frequency_Cepstral_Coefficients_MFCCs_">Computing Mel-Frequency Cepstral Coefficients (MFCCs)</h2>

Call <a href="../../api_docs/python/tf/contrib/signal/mfccs_from_log_mel_spectrograms.md"><code>tf.contrib.signal.mfccs_from_log_mel_spectrograms</code></a> to compute
[MFCCs][mfcc] from log-magnitude, mel-scale spectrograms (as computed in the
preceding example):

```python
num_mfccs = 13
# Keep the first `num_mfccs` MFCCs.
mfccs = tf.contrib.signal.mfccs_from_log_mel_spectrograms(
    log_mel_spectrograms)[..., :num_mfccs]
```

[stft]: https://en.wikipedia.org/wiki/Short-time_Fourier_transform
[mel]: https://en.wikipedia.org/wiki/Mel_scale
[mfcc]: https://en.wikipedia.org/wiki/Mel-frequency_cepstrum
