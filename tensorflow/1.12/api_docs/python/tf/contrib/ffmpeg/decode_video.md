<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.ffmpeg.decode_video" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.ffmpeg.decode_video

``` python
tf.contrib.ffmpeg.decode_video(contents)
```



Defined in [`tensorflow/contrib/ffmpeg/ffmpeg_ops.py`](/code/stable/tensorflow/contrib/ffmpeg/ffmpeg_ops.py).

Create an op that decodes the contents of a video file. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed after 2018-09-04.
Instructions for updating:
This will be deleted and should not be used.

#### Args:

* <b>`contents`</b>: The binary contents of the video file to decode. This is a
    scalar.


#### Returns:

A rank-4 `Tensor` that has `[frames, height, width, 3]` RGB as output.