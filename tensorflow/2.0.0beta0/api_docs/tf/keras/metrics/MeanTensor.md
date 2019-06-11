<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.MeanTensor" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="count"/>
<meta itemprop="property" content="total"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="result"/>
<meta itemprop="property" content="update_state"/>
</div>

# tf.keras.metrics.MeanTensor

## Class `MeanTensor`

Computes the element-wise (weighted) mean of the given tensors.

Inherits From: [`Metric`](../../../tf/keras/metrics/Metric.md)

### Aliases:

* Class `tf.compat.v1.keras.metrics.MeanTensor`
* Class `tf.compat.v2.keras.metrics.MeanTensor`
* Class `tf.compat.v2.metrics.MeanTensor`
* Class `tf.keras.metrics.MeanTensor`
* Class `tf.metrics.MeanTensor`



Defined in [`python/keras/metrics.py`](/code/stable/tensorflow/python/keras/metrics.py).

<!-- Placeholder for "Used in" -->

`MeanTensor` returns a tensor with the same shape of the input tensors. The
mean value is updated by keeping local variables `total` and `count`. The
`total` tracks the sum of the weighted values, and `count` stores the sum of
the weighted counts.

#### Usage:



```python
m = tf.keras.metrics.MeanTensor()
m.update_state([0, 1, 2, 3])
m.update_state([4, 5, 6, 7])
print('Result: ', m.result().numpy())  # Result: [2, 3, 4, 5]
m.update_state([12, 10, 8, 6], sample_weights= [0, 0.2, 0.5, 1])
print('Result: ', m.result().numpy())  # Result: [2, 3.636, 4.8, 5.333]
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    name='mean_tensor',
    dtype=None
)
```

Creates a `MeanTensor` instance.


#### Args:


* <b>`name`</b>: (Optional) string name of the metric instance.
* <b>`dtype`</b>: (Optional) data type of the metric result.



## Properties

<h3 id="count"><code>count</code></h3>




<h3 id="total"><code>total</code></h3>






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
    values,
    sample_weight=None
)
```

Accumulates statistics for computing the element-wise mean.


#### Args:


* <b>`values`</b>: Per-example value.
* <b>`sample_weight`</b>: Optional weighting of each example. Defaults to 1.


#### Returns:

Update op.




