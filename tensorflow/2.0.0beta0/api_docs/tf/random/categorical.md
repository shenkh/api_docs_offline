<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.random.categorical" />
<meta itemprop="path" content="Stable" />
</div>

# tf.random.categorical

Draws samples from a categorical distribution.

### Aliases:

* `tf.compat.v1.random.categorical`
* `tf.compat.v2.random.categorical`
* `tf.random.categorical`

``` python
tf.random.categorical(
    logits,
    num_samples,
    dtype=None,
    seed=None,
    name=None
)
```



Defined in [`python/ops/random_ops.py`](/code/stable/tensorflow/python/ops/random_ops.py).

<!-- Placeholder for "Used in" -->


#### Example:



```python
# samples has shape [1, 5], where each value is either 0 or 1 with equal
# probability.
samples = tf.random.categorical(tf.math.log([[10., 10.]]), 5)
```

#### Args:


* <b>`logits`</b>: 2-D Tensor with shape `[batch_size, num_classes]`.  Each slice
  `[i, :]` represents the unnormalized log-probabilities for all classes.
* <b>`num_samples`</b>: 0-D.  Number of independent samples to draw for each row slice.
* <b>`dtype`</b>: integer type to use for the output. Defaults to int64.
* <b>`seed`</b>: A Python integer. Used to create a random seed for the distribution.
  See <a href="../../tf/compat/v1/set_random_seed.md"><code>tf.compat.v1.set_random_seed</code></a> for behavior.
* <b>`name`</b>: Optional name for the operation.


#### Returns:

The drawn samples of shape `[batch_size, num_samples]`.
