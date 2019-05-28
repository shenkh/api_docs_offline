# FFmpeg (contrib)
[TOC]

<h2 id="Encoding_and_decoding_audio_using_FFmpeg">Encoding and decoding audio using FFmpeg</h2>

TensorFlow provides Ops to decode and encode audio files using the
[FFmpeg](https://www.ffmpeg.org/) library. FFmpeg must be
locally [installed](https://ffmpeg.org/download.html) for these Ops to succeed.

Example:

```python
from tensorflow.contrib import ffmpeg

audio_binary = tf.read_file('song.mp3')
waveform = ffmpeg.decode_audio(
    audio_binary, file_format='mp3', samples_per_second=44100, channel_count=2)
uncompressed_binary = ffmpeg.encode_audio(
    waveform, file_format='wav', samples_per_second=44100)
```

*   <a href="../../api_docs/python/tf/contrib/ffmpeg/decode_audio.md"><code>tf.contrib.ffmpeg.decode_audio</code></a>
*   <a href="../../api_docs/python/tf/contrib/ffmpeg/encode_audio.md"><code>tf.contrib.ffmpeg.encode_audio</code></a>
