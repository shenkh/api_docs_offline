<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.ffmpeg.decode_video" />
</div>

# tf.contrib.ffmpeg.decode_video

``` python
tf.contrib.ffmpeg.decode_video(contents)
```



Defined in [`tensorflow/contrib/ffmpeg/ffmpeg_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/ffmpeg/ffmpeg_ops.py).

Create an op that decodes the contents of a video file.

#### Args:

* <b>`contents`</b>: The binary contents of the video file to decode. This is a
    scalar.


#### Returns:

A rank-4 `Tensor` that has `[frames, height, width, 3]` RGB as output.