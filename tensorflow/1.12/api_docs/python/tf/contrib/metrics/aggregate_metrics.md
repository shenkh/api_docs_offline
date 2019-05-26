<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.metrics.aggregate_metrics" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.metrics.aggregate_metrics

``` python
tf.contrib.metrics.aggregate_metrics(*value_update_tuples)
```



Defined in [`tensorflow/contrib/metrics/python/ops/metric_ops.py`](/code/stable/tensorflow/contrib/metrics/python/ops/metric_ops.py).

Aggregates the metric value tensors and update ops into two lists.

#### Args:

* <b>`*value_update_tuples`</b>: a variable number of tuples, each of which contain the
    pair of (value_tensor, update_op) from a streaming metric.


#### Returns:

A list of value `Tensor` objects and a list of update ops.


#### Raises:

* <b>`ValueError`</b>: if `value_update_tuples` is empty.