<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.Mean" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="result"/>
<meta itemprop="property" content="update_state"/>
</div>

# tf.keras.metrics.Mean

## Class `Mean`

Computes the (weighted) mean of the given values.



### Aliases:

* Class `tf.compat.v1.keras.metrics.Mean`
* Class `tf.compat.v2.keras.metrics.Mean`
* Class `tf.compat.v2.metrics.Mean`
* Class `tf.keras.metrics.Mean`
* Class `tf.metrics.Mean`



Defined in [`python/keras/metrics.py`](/code/stable/tensorflow/python/keras/metrics.py).

<!-- Placeholder for "Used in" -->

For example, if values is [1, 3, 5, 7] then the mean is 4.
If the weights were specified as [1, 1, 0, 0] then the mean would be 2.

This metric creates two variables, `total` and `count` that are used to
compute the average of `values`. This average is ultimately returned as `mean`
which is an idempotent operation that simply divides `total` by `count`.

If `sample_weight` is `None`, weights default to 1.
Use `sample_weight` of 0 to mask values.

#### Usage:



```python
m = tf.keras.metrics.Mean()
m.update_state([1, 3, 5, 7])
print('Final result: ', m.result().numpy())  # Final result: 4.0
```

Usage with tf.keras API:

```python
model = tf.keras.Model(inputs, outputs)
model.add_metric(tf.keras.metrics.Mean(name='mean_1')(outputs))
model.compile('sgd', loss='mse')
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    name='mean',
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
    values,
    sample_weight=None
)
```

Accumulates statistics for computing the reduction metric.

For example, if `values` is [1, 3, 5, 7] and reduction=SUM_OVER_BATCH_SIZE,
then the value of `result()` is 4. If the `sample_weight` is specified as
[1, 1, 0, 0] then value of `result()` would be 2.

#### Args:


* <b>`values`</b>: Per-example value.
* <b>`sample_weight`</b>: Optional weighting of each example. Defaults to 1.


#### Returns:

Update op.




