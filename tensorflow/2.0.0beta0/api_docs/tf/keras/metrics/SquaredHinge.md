<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.SquaredHinge" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="result"/>
<meta itemprop="property" content="update_state"/>
</div>

# tf.keras.metrics.SquaredHinge

## Class `SquaredHinge`

Computes the squared hinge metric between `y_true` and `y_pred`.



### Aliases:

* Class `tf.compat.v1.keras.metrics.SquaredHinge`
* Class `tf.compat.v2.keras.metrics.SquaredHinge`
* Class `tf.compat.v2.metrics.SquaredHinge`
* Class `tf.keras.metrics.SquaredHinge`
* Class `tf.metrics.SquaredHinge`



Defined in [`python/keras/metrics.py`](/code/stable/tensorflow/python/keras/metrics.py).

<!-- Placeholder for "Used in" -->

`y_true` values are expected to be -1 or 1. If binary (0 or 1) labels are
provided we will convert them to -1 or 1.

For example, if `y_true` is [-1., 1., 1.], and `y_pred` is [0.6, -0.7, -0.5]
the squared hinge metric value is 2.6.

#### Usage:



```python
m = tf.keras.metrics.SquaredHinge()
m.update_state([-1., 1., 1.], [0.6, -0.7, -0.5])

# result = max(0, 1-y_true * y_pred) = [1.6^2 + 1.7^2 + 1.5^2] / 3

print('Final result: ', m.result().numpy())  # Final result: 2.6
```

Usage with tf.keras API:

```python
model = tf.keras.Model(inputs, outputs)
model.compile('sgd', metrics=[tf.keras.metrics.SquaredHinge()])
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    name='squared_hinge',
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




