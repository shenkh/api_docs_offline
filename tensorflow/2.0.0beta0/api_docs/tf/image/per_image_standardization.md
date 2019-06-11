<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.per_image_standardization" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.per_image_standardization

Linearly scales each image in `image` to have mean 0 and variance 1.

### Aliases:

* `tf.compat.v1.image.per_image_standardization`
* `tf.compat.v2.image.per_image_standardization`
* `tf.image.per_image_standardization`

``` python
tf.image.per_image_standardization(image)
```



Defined in [`python/ops/image_ops_impl.py`](/code/stable/tensorflow/python/ops/image_ops_impl.py).

<!-- Placeholder for "Used in" -->

For each 3-D image `x` in `image`, computes `(x - mean) / adjusted_stddev`,
where

- `mean` is the average of all values in `x`
- `adjusted_stddev = max(stddev, 1.0/sqrt(N))` is capped away from 0 to
  protect against division by 0 when handling uniform images
  - `N` is the number of elements in `x`
  - `stddev` is the standard deviation of all values in `x`

#### Args:


* <b>`image`</b>: An n-D Tensor with at least 3 dimensions, the last 3 of which are the
  dimensions of each image.


#### Returns:

A `Tensor` with same shape and dtype as `image`.



#### Raises:


* <b>`ValueError`</b>: if the shape of 'image' is incompatible with this function.