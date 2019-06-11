<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.MeanAbsolutePercentageError" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="result"/>
<meta itemprop="property" content="update_state"/>
</div>

# tf.keras.metrics.MeanAbsolutePercentageError

## Class `MeanAbsolutePercentageError`

Computes the mean absolute percentage error between `y_true` and `y_pred`.



### Aliases:

* Class `tf.compat.v1.keras.metrics.MeanAbsolutePercentageError`
* Class `tf.compat.v2.keras.metrics.MeanAbsolutePercentageError`
* Class `tf.compat.v2.metrics.MeanAbsolutePercentageError`
* Class `tf.keras.metrics.MeanAbsolutePercentageError`
* Class `tf.metrics.MeanAbsolutePercentageError`



Defined in [`python/keras/metrics.py`](/code/stable/tensorflow/python/keras/metrics.py).

<!-- Placeholder for "Used in" -->

For example, if `y_true` is [0., 0., 1., 1.], and `y_pred` is [1., 1., 1., 0.]
the mean absolute percentage error is 5e+08.

#### Usage:



```python
m = tf.keras.metrics.MeanAbsolutePercentageError()
m.update_state([0., 0., 1., 1.], [1., 1., 1., 0.])
print('Final result: ', m.result().numpy())  # Final result: 5e+08
```

Usage with tf.keras API:

```python
model = tf.keras.Model(inputs, outputs)
model.compile('sgd', metrics=[tf.keras.metrics.MeanAbsolutePercentageError()])
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    name='mean_absolute_percentage_error',
    dtype=None
)
```

Creates a `MeanMetricWrapper` instance.


#### Args:


* <b>`fn`</b>: The metric function to wrap, with signature
  `fn(y_true, y_pred, **kwargs)`.
* <b>`name`</b>: (Optional) string name of the metric instance.
* <b>`dtype`</b>: (Optional) data type of the metric result.
* <b>`**kwargs`</b>: The keyword arguments that are passed on to `fn`.



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

`y_true` and `y_pred` should have the same shape.

#### Args:


* <b>`y_true`</b>: The ground truth values.
* <b>`y_pred`</b>: The predicted values.
* <b>`sample_weight`</b>: Optional weighting of each example. Defaults to 1. Can be
  a `Tensor` whose rank is either 0, or the same rank as `y_true`,
  and must be broadcastable to `y_true`.


#### Returns:

Update op.




