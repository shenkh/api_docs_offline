<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.hsv_to_rgb" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.hsv_to_rgb

Convert one or more images from HSV to RGB.

### Aliases:

* `tf.compat.v1.image.hsv_to_rgb`
* `tf.compat.v2.image.hsv_to_rgb`
* `tf.image.hsv_to_rgb`

``` python
tf.image.hsv_to_rgb(
    images,
    name=None
)
```



Defined in generated file: `python/ops/gen_image_ops.py`.

<!-- Placeholder for "Used in" -->

Outputs a tensor of the same shape as the `images` tensor, containing the RGB
value of the pixels. The output is only well defined if the value in `images`
are in `[0,1]`.

See `rgb_to_hsv` for a description of the HSV encoding.

#### Args:


* <b>`images`</b>: A `Tensor`. Must be one of the following types: `half`, `bfloat16`, `float32`, `float64`.
  1-D or higher rank. HSV data to convert. Last dimension must be size 3.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `images`.
