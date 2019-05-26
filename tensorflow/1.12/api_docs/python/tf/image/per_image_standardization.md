<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.per_image_standardization" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.per_image_standardization

``` python
tf.image.per_image_standardization(image)
```



Defined in [`tensorflow/python/ops/image_ops_impl.py`](/code/stable/tensorflow/python/ops/image_ops_impl.py).

Linearly scales `image` to have zero mean and unit variance.

This op computes `(x - mean) / adjusted_stddev`, where `mean` is the average
of all values in image, and
`adjusted_stddev = max(stddev, 1.0/sqrt(image.NumElements()))`.

`stddev` is the standard deviation of all values in `image`. It is capped
away from zero to protect against division by 0 when handling uniform images.

#### Args:

* <b>`image`</b>: 3-D tensor of shape `[height, width, channels]`.


#### Returns:

The standardized image with same shape as `image`.


#### Raises:

* <b>`ValueError`</b>: if the shape of 'image' is incompatible with this function.