<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.random_contrast" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.random_contrast

Adjust the contrast of an image or images by a random factor.

### Aliases:

* `tf.compat.v1.image.random_contrast`
* `tf.compat.v2.image.random_contrast`
* `tf.image.random_contrast`

``` python
tf.image.random_contrast(
    image,
    lower,
    upper,
    seed=None
)
```



Defined in [`python/ops/image_ops_impl.py`](/code/stable/tensorflow/python/ops/image_ops_impl.py).

<!-- Placeholder for "Used in" -->

Equivalent to `adjust_contrast()` but uses a `contrast_factor` randomly
picked in the interval `[lower, upper]`.

#### Args:


* <b>`image`</b>: An image tensor with 3 or more dimensions.
* <b>`lower`</b>: float.  Lower bound for the random contrast factor.
* <b>`upper`</b>: float.  Upper bound for the random contrast factor.
* <b>`seed`</b>: A Python integer. Used to create a random seed. See
  <a href="../../tf/compat/v1/set_random_seed.md"><code>tf.compat.v1.set_random_seed</code></a> for behavior.


#### Returns:

The contrast-adjusted image(s).



#### Raises:


* <b>`ValueError`</b>: if `upper <= lower` or if `lower < 0`.