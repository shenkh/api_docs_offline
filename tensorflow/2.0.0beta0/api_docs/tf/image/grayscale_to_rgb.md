<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.grayscale_to_rgb" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.grayscale_to_rgb

Converts one or more images from Grayscale to RGB.

### Aliases:

* `tf.compat.v1.image.grayscale_to_rgb`
* `tf.compat.v2.image.grayscale_to_rgb`
* `tf.image.grayscale_to_rgb`

``` python
tf.image.grayscale_to_rgb(
    images,
    name=None
)
```



Defined in [`python/ops/image_ops_impl.py`](/code/stable/tensorflow/python/ops/image_ops_impl.py).

<!-- Placeholder for "Used in" -->

Outputs a tensor of the same `DType` and rank as `images`.  The size of the
last dimension of the output is 3, containing the RGB value of the pixels.
The input images' last dimension must be size 1.

#### Args:


* <b>`images`</b>: The Grayscale tensor to convert. Last dimension must be size 1.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The converted grayscale image(s).
