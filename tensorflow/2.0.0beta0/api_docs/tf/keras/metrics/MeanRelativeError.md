<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.MeanRelativeError" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="result"/>
<meta itemprop="property" content="update_state"/>
</div>

# tf.keras.metrics.MeanRelativeError

## Class `MeanRelativeError`

Computes the mean relative error by normalizing with the given values.

Inherits From: [`Mean`](../../../tf/keras/metrics/Mean.md)

### Aliases:

* Class `tf.compat.v1.keras.metrics.MeanRelativeError`
* Class `tf.compat.v2.keras.metrics.MeanRelativeError`
* Class `tf.compat.v2.metrics.MeanRelativeError`
* Class `tf.keras.metrics.MeanRelativeError`
* Class `tf.metrics.MeanRelativeError`



Defined in [`python/keras/metrics.py`](/code/stable/tensorflow/python/keras/metrics.py).

<!-- Placeholder for "Used in" -->

This metric creates two local variables, `total` and `count` that are used to
compute the mean relative absolute error. This average is weighted by
`sample_weight`, and it is ultimately returned as `mean_relative_error`:
an idempotent operation that simply divides `total` by `count`.

If `sample_weight` is `None`, weights default to 1.
Use `sample_weight` of 0 to mask values.

#### Usage:



```python
m = tf.keras.metrics.MeanRelativeError(normalizer=[1, 3, 2, 3])
m.update_state([1, 3, 2, 3], [2, 4, 6, 8])

# metric = mean(|y_pred - y_true| / normalizer)
#        = mean([1, 1, 4, 5] / [1, 3, 2, 3]) = mean([1, 1/3, 2, 5/3])
#        = 5/4 = 1.25
print('Final result: ', m.result().numpy())  # Final result: 1.25
```

Usage with tf.keras API:

```python
model = tf.keras.Model(inputs, outputs)
model.compile(
  'sgd',
  loss='mse',
  metrics=[tf.keras.metrics.MeanRelativeError(normalizer=[1, 3])])
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    normalizer,
    name=None,
    dtype=None
)
```

Creates a `MeanRelativeError` instance.


#### Args:


* <b>`normalizer`</b>: The normalizer values with same shape as predictions.
* <b>`name`</b>: (Optional) string name of the metric instance.
* <b>`dtype`</b>: (Optional) data type of the metric result.



## Methods

<h3 id="reset_states"><code>reset_states</code></h3>

``` python
reset_states()
```

Resets all of the metric state variables.

This function is called between epochs/steps,
when a metric is evaluated during training.

<h3 id="result"><code>result</code></h3>

``` python
result()
```

Computes and returns the metric value tensor.

Result computation is an idempotent operation that simply calculates the
metric value using the state variables.

<h3 id="update_state"><code>update_state</code></h3>

``` python
update_state(
    y_true,
    y_pred,
    sample_weight=None
)
```

Accumulates metric statistics.


#### Args:


* <b>`y_true`</b>: The ground truth values.
* <b>`y_pred`</b>: The predicted values.
* <b>`sample_weight`</b>: Optional weighting of each example. Defaults to 1. Can be a
  `Tensor` whose rank is either 0, or the same rank as `y_true`, and must
  be broadcastable to `y_true`.


#### Returns:

Update op.




