<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.adjust_gamma" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.adjust_gamma

``` python
tf.image.adjust_gamma(
    image,
    gamma=1,
    gain=1
)
```



Defined in [`tensorflow/python/ops/image_ops_impl.py`](/code/stable/tensorflow/python/ops/image_ops_impl.py).

Performs Gamma Correction on the input image.

Also known as Power Law Transform. This function converts the
input images at first to float representation, then transforms them
pixelwise according to the equation `Out = gain * In**gamma`,
and then converts the back to the original data type.

#### Args:

* <b>`image `</b>: RGB image or images to adjust.
* <b>`gamma `</b>: A scalar or tensor. Non negative real number.
* <b>`gain  `</b>: A scalar or tensor. The constant multiplier.


#### Returns:

  A Tensor. A Gamma-adjusted tensor of the same shape and type as `image`.
Usage Example:
  ```python
  >> import tensorflow as tf
  >> x = tf.random.normal(shape=(256, 256, 3))
  >> tf.image.adjust_gamma(x, 0.2)
  ```

#### Raises:

* <b>`ValueError`</b>: If gamma is negative.
Notes:
  For gamma greater than 1, the histogram will shift towards left and
  the output image will be darker than the input image.
  For gamma less than 1, the histogram will shift towards right and
  the output image will be brighter than the input image.
References:
  [1] http://en.wikipedia.org/wiki/Gamma_correction