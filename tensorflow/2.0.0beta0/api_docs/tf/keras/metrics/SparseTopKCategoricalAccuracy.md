<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.SparseTopKCategoricalAccuracy" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="result"/>
<meta itemprop="property" content="update_state"/>
</div>

# tf.keras.metrics.SparseTopKCategoricalAccuracy

## Class `SparseTopKCategoricalAccuracy`

Computes how often integer targets are in the top `K` predictions.



### Aliases:

* Class `tf.compat.v1.keras.metrics.SparseTopKCategoricalAccuracy`
* Class `tf.compat.v2.keras.metrics.SparseTopKCategoricalAccuracy`
* Class `tf.compat.v2.metrics.SparseTopKCategoricalAccuracy`
* Class `tf.keras.metrics.SparseTopKCategoricalAccuracy`
* Class `tf.metrics.SparseTopKCategoricalAccuracy`



Defined in [`python/keras/metrics.py`](/code/stable/tensorflow/python/keras/metrics.py).

<!-- Placeholder for "Used in" -->


#### Usage:



```python
m = tf.keras.metrics.SparseTopKCategoricalAccuracy()
m.update_state([2, 1], [[0.1, 0.9, 0.8], [0.05, 0.95, 0]])
print('Final result: ', m.result().numpy())  # Final result: 1.0
```

Usage with tf.keras API:

```python
model = tf.keras.Model(inputs, outputs)
model.compile(
  'sgd',
  metrics=[tf.keras.metrics.SparseTopKCategoricalAccuracy()])
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    k=5,
    name='sparse_top_k_categorical_accuracy',
    dtype=None
)
```

Creates a `SparseTopKCategoricalAccuracy` instance.


#### Args:


* <b>`k`</b>: (Optional) Number of top elements to look at for computing accuracy.
  Defaults to 5.
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

`y_true` and `y_pred` should have the same shape.

#### Args:


* <b>`y_true`</b>: The ground truth values.
* <b>`y_pred`</b>: The predicted values.
* <b>`sample_weight`</b>: Optional weighting of each example. Defaults to 1. Can be
  a `Tensor` whose rank is either 0, or the same rank as `y_true`,
  and must be broadcastable to `y_true`.


#### Returns:

Update op.




