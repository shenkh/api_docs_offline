<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.random_hue" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.random_hue

Adjust the hue of RGB images by a random factor.

### Aliases:

* `tf.compat.v1.image.random_hue`
* `tf.compat.v2.image.random_hue`
* `tf.image.random_hue`

``` python
tf.image.random_hue(
    image,
    max_delta,
    seed=None
)
```



Defined in [`python/ops/image_ops_impl.py`](/code/stable/tensorflow/python/ops/image_ops_impl.py).

<!-- Placeholder for "Used in" -->

Equivalent to `adjust_hue()` but uses a `delta` randomly
picked in the interval `[-max_delta, max_delta]`.

`max_delta` must be in the interval `[0, 0.5]`.

#### Args:


* <b>`image`</b>: RGB image or images. Size of the last dimension must be 3.
* <b>`max_delta`</b>: float.  Maximum value for the random delta.
* <b>`seed`</b>: An operation-specific seed. It will be used in conjunction with the
  graph-level seed to determine the real seeds that will be used in this
  operation. Please see the documentation of set_random_seed for its
  interaction with the graph-level random seed.


#### Returns:

Adjusted image(s), same shape and DType as `image`.



#### Raises:


* <b>`ValueError`</b>: if `max_delta` is invalid.