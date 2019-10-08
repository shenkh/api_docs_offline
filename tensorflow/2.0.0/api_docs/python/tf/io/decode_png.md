<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.decode_png" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.decode_png

### Aliases:

* `tf.image.decode_png`
* `tf.io.decode_png`

``` python
tf.io.decode_png(
    contents,
    channels=0,
    dtype=tf.dtypes.uint8,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_image_ops.py`.

Decode a PNG-encoded image to a uint8 or uint16 tensor.

The attr `channels` indicates the desired number of color channels for the
decoded image.

Accepted values are:

*   0: Use the number of channels in the PNG-encoded image.
*   1: output a grayscale image.
*   3: output an RGB image.
*   4: output an RGBA image.

If needed, the PNG-encoded image is transformed to match the requested number
of color channels.

This op also supports decoding JPEGs and non-animated GIFs since the interface
is the same, though it is cleaner to use <a href="../../tf/io/decode_image.md"><code>tf.image.decode_image</code></a>.

#### Args:

* <b>`contents`</b>: A `Tensor` of type `string`. 0-D.  The PNG-encoded image.
* <b>`channels`</b>: An optional `int`. Defaults to `0`.
    Number of color channels for the decoded image.
* <b>`dtype`</b>: An optional <a href="../../tf/dtypes/DType.md"><code>tf.DType</code></a> from: `tf.uint8, tf.uint16`. Defaults to <a href="../../tf/dtypes.md#uint8"><code>tf.uint8</code></a>.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `dtype`.