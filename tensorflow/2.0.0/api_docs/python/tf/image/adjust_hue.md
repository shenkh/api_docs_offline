<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.adjust_hue" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.adjust_hue

``` python
tf.image.adjust_hue(
    image,
    delta,
    name=None
)
```



Defined in [`tensorflow/python/ops/image_ops_impl.py`](/code/stable/tensorflow/python/ops/image_ops_impl.py).

Adjust hue of RGB images.

This is a convenience method that converts an RGB image to float
representation, converts it to HSV, add an offset to the hue channel, converts
back to RGB and then back to the original data type. If several adjustments
are chained it is advisable to minimize the number of redundant conversions.

`image` is an RGB image.  The image hue is adjusted by converting the
image(s) to HSV and rotating the hue channel (H) by
`delta`.  The image is then converted back to RGB.

`delta` must be in the interval `[-1, 1]`.

#### Args:

* <b>`image`</b>: RGB image or images. Size of the last dimension must be 3.
* <b>`delta`</b>: float.  How much to add to the hue channel.
* <b>`name`</b>: A name for this operation (optional).


#### Returns:

  Adjusted image(s), same shape and DType as `image`.

Usage Example:
  ```python
  >> import tensorflow as tf
  >> x = tf.random.normal(shape=(256, 256, 3))
  >> tf.image.adjust_hue(x, 0.2)
  ```