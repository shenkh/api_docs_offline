<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.random_contrast" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.random_contrast

``` python
tf.image.random_contrast(
    image,
    lower,
    upper,
    seed=None
)
```



Defined in [`tensorflow/python/ops/image_ops_impl.py`](/code/stable/tensorflow/python/ops/image_ops_impl.py).

Adjust the contrast of an image or images by a random factor.

Equivalent to `adjust_contrast()` but uses a `contrast_factor` randomly
picked in the interval `[lower, upper]`.

#### Args:

* <b>`image`</b>: An image tensor with 3 or more dimensions.
* <b>`lower`</b>: float.  Lower bound for the random contrast factor.
* <b>`upper`</b>: float.  Upper bound for the random contrast factor.
* <b>`seed`</b>: A Python integer. Used to create a random seed. See
    `tf.compat.v1.set_random_seed` for behavior.


#### Returns:

The contrast-adjusted image(s).


#### Raises:

* <b>`ValueError`</b>: if `upper <= lower` or if `lower < 0`.