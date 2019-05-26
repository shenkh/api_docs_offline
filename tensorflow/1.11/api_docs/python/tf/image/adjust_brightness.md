<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.adjust_brightness" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.adjust_brightness

``` python
tf.image.adjust_brightness(
    image,
    delta
)
```



Defined in [`tensorflow/python/ops/image_ops_impl.py`](https://www.tensorflow.org/code/tensorflow/python/ops/image_ops_impl.py).

See the guide: [Images > Image Adjustments](../../../../api_guides/python/image.md#Image_Adjustments)

Adjust the brightness of RGB or Grayscale images.

This is a convenience method that converts an RGB image to float
representation, adjusts its brightness, and then converts it back to the
original data type. If several adjustments are chained it is advisable to
minimize the number of redundant conversions.

The value `delta` is added to all components of the tensor `image`. Both
`image` and `delta` are converted to `float` before adding (and `image` is
scaled appropriately if it is in fixed-point representation). For regular
images, `delta` should be in the range `[0,1)`, as it is added to the image in
floating point representation, where pixel values are in the `[0,1)` range.

#### Args:

* <b>`image`</b>: A tensor.
* <b>`delta`</b>: A scalar. Amount to add to the pixel values.


#### Returns:

A brightness-adjusted tensor of the same shape and type as `image`.