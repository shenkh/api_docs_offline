<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.resize_nearest_neighbor" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.resize_nearest_neighbor

``` python
tf.image.resize_nearest_neighbor(
    images,
    size,
    align_corners=False,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_image_ops.py`.

Resize `images` to `size` using nearest neighbor interpolation.

#### Args:

* <b>`images`</b>: A `Tensor`. Must be one of the following types: `int8`, `uint8`, `int16`, `uint16`, `int32`, `int64`, `half`, `float32`, `float64`.
    4-D with shape `[batch, height, width, channels]`.
* <b>`size`</b>:  A 1-D int32 Tensor of 2 elements: `new_height, new_width`.  The
    new size for the images.
* <b>`align_corners`</b>: An optional `bool`. Defaults to `False`.
    If true, the centers of the 4 corner pixels of the input and output tensors are
    aligned, preserving the values at the corner pixels. Defaults to false.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `images`.