<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.per_image_standardization" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.per_image_standardization

``` python
tf.image.per_image_standardization(image)
```



Defined in [`tensorflow/python/ops/image_ops_impl.py`](https://www.tensorflow.org/code/tensorflow/python/ops/image_ops_impl.py).

See the guides: [Images > Image Adjustments](../../../../api_guides/python/image.md#Image_Adjustments), [Upgrade to TensorFlow 1.0 > Upgrading your code manually](../../../../api_guides/python/upgrade.md#Upgrading_your_code_manually)

Linearly scales `image` to have zero mean and unit norm.

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