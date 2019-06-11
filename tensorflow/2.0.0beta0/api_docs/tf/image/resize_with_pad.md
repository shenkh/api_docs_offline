<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.resize_with_pad" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.resize_with_pad

Resizes and pads an image to a target width and height.

### Aliases:

* `tf.compat.v2.image.resize_with_pad`
* `tf.image.resize_with_pad`

``` python
tf.image.resize_with_pad(
    image,
    target_height,
    target_width,
    method=ResizeMethod.BILINEAR,
    antialias=False
)
```



Defined in [`python/ops/image_ops_impl.py`](/code/stable/tensorflow/python/ops/image_ops_impl.py).

<!-- Placeholder for "Used in" -->

Resizes an image to a target width and height by keeping
the aspect ratio the same without distortion. If the target
dimensions don't match the image dimensions, the image
is resized and then padded with zeroes to match requested
dimensions.

#### Args:


* <b>`image`</b>: 4-D Tensor of shape `[batch, height, width, channels]` or 3-D Tensor
  of shape `[height, width, channels]`.
* <b>`target_height`</b>: Target height.
* <b>`target_width`</b>: Target width.
* <b>`method`</b>: Method to use for resizing image. See `image.resize()`
* <b>`antialias`</b>: Whether to use anti-aliasing when resizing. See 'image.resize()'.


#### Raises:


* <b>`ValueError`</b>: if `target_height` or `target_width` are zero or negative.


#### Returns:

Resized and padded image.
If `images` was 4-D, a 4-D float Tensor of shape
`[batch, new_height, new_width, channels]`.
If `images` was 3-D, a 3-D float Tensor of shape
`[new_height, new_width, channels]`.
