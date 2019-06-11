<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.signal.inverse_stft" />
<meta itemprop="path" content="Stable" />
</div>

# tf.signal.inverse_stft

Computes the inverse [Short-time Fourier Transform][stft] of `stfts`.

### Aliases:

* `tf.compat.v1.signal.inverse_stft`
* `tf.compat.v2.signal.inverse_stft`
* `tf.signal.inverse_stft`

``` python
tf.signal.inverse_stft(
    stfts,
    frame_length,
    frame_step,
    fft_length=None,
    window_fn=tf.signal.hann_window,
    name=None
)
```



Defined in [`python/ops/signal/spectral_ops.py`](/code/stable/tensorflow/python/ops/signal/spectral_ops.py).

<!-- Placeholder for "Used in" -->

To reconstruct an original waveform, a complimentary window function should
be used in inverse_stft. Such a window function can be constructed with
tf.signal.inverse_stft_window_fn.

#### Example:



```python
frame_length = 400
frame_step = 160
waveform = tf.compat.v1.placeholder(dtype=tf.float32, shape=[1000])
stft = tf.signal.stft(waveform, frame_length, frame_step)
inverse_stft = tf.signal.inverse_stft(
    stft, frame_length, frame_step,
    window_fn=tf.signal.inverse_stft_window_fn(frame_step))
```

if a custom window_fn is used in stft, it must be passed to
inverse_stft_window_fn:

```python
frame_length = 400
frame_step = 160
window_fn = functools.partial(window_ops.hamming_window, periodic=True),
waveform = tf.compat.v1.placeholder(dtype=tf.float32, shape=[1000])
stft = tf.signal.stft(
    waveform, frame_length, frame_step, window_fn=window_fn)
inverse_stft = tf.signal.inverse_stft(
    stft, frame_length, frame_step,
    window_fn=tf.signal.inverse_stft_window_fn(
       frame_step, forward_window_fn=window_fn))
```

Implemented with GPU-compatible ops and supports gradients.

#### Args:


* <b>`stfts`</b>: A `complex64` `[..., frames, fft_unique_bins]` `Tensor` of STFT bins
  representing a batch of `fft_length`-point STFTs where `fft_unique_bins`
  is `fft_length // 2 + 1`
* <b>`frame_length`</b>: An integer scalar `Tensor`. The window length in samples.
* <b>`frame_step`</b>: An integer scalar `Tensor`. The number of samples to step.
* <b>`fft_length`</b>: An integer scalar `Tensor`. The size of the FFT that produced
  `stfts`. If not provided, uses the smallest power of 2 enclosing
  `frame_length`.
* <b>`window_fn`</b>: A callable that takes a window length and a `dtype` keyword
  argument and returns a `[window_length]` `Tensor` of samples in the
  provided datatype. If set to `None`, no windowing is used.
* <b>`name`</b>: An optional name for the operation.


#### Returns:

A `[..., samples]` `Tensor` of `float32` signals representing the inverse
STFT for each input STFT in `stfts`.



#### Raises:


* <b>`ValueError`</b>: If `stfts` is not at least rank 2, `frame_length` is not scalar,
  `frame_step` is not scalar, or `fft_length` is not scalar.

[stft]: https://en.wikipedia.org/wiki/Short-time_Fourier_transform