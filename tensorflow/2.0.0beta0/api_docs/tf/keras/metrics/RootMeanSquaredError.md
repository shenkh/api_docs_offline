<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.RootMeanSquaredError" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="result"/>
<meta itemprop="property" content="update_state"/>
</div>

# tf.keras.metrics.RootMeanSquaredError

## Class `RootMeanSquaredError`

Computes root mean squared error metric between `y_true` and `y_pred`.

Inherits From: [`Mean`](../../../tf/keras/metrics/Mean.md)

### Aliases:

* Class `tf.compat.v1.keras.metrics.RootMeanSquaredError`
* Class `tf.compat.v2.keras.metrics.RootMeanSquaredError`
* Class `tf.compat.v2.metrics.RootMeanSquaredError`
* Class `tf.keras.metrics.RootMeanSquaredError`
* Class `tf.metrics.RootMeanSquaredError`



Defined in [`python/keras/metrics.py`](/code/stable/tensorflow/python/keras/metrics.py).

<!-- Placeholder for "Used in" -->


#### Usage:



```python
m = tf.keras.metrics.RootMeanSquaredError()
m.update_state([2., 4., 6.], [1., 3., 2.])
print('Final result: ', m.result().numpy())  # Final result: 2.449
```

Usage with tf.keras API:

```python
model = tf.keras.Model(inputs, outputs)
model.compile('sgd', metrics=[tf.keras.metrics.RootMeanSquaredError()])
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    name='root_mean_squared_error',
    dtype=None
)
```

Creates a `Mean` instance.


#### Args:


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

Accumulates root mean squared error statistics.


#### Args:


* <b>`y_true`</b>: The ground truth values.
* <b>`y_pred`</b>: The predicted values.
* <b>`sample_weight`</b>: Optional weighting of each example. Defaults to 1. Can be a
  `Tensor` whose rank is either 0, or the same rank as `y_true`, and must
  be broadcastable to `y_true`.


#### Returns:

Update op.



