<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.metrics.count" />
</div>

# tf.contrib.metrics.count

``` python
tf.contrib.metrics.count(
    values,
    weights=None,
    metrics_collections=None,
    updates_collections=None,
    name=None
)
```



Defined in [`tensorflow/contrib/metrics/python/ops/metric_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/metrics/python/ops/metric_ops.py).

Computes the number of examples, or sum of `weights`.

When evaluating some metric (e.g. mean) on one or more subsets of the data,
this auxiliary metric is useful for keeping track of how many examples there
are in each subset.

If `weights` is `None`, weights default to 1. Use weights of 0 to mask values.

#### Args:

* <b>`values`</b>: A `Tensor` of arbitrary dimensions. Only it's shape is used.
* <b>`weights`</b>: Optional `Tensor` whose rank is either 0, or the same rank as
    `labels`, and must be broadcastable to `labels` (i.e., all dimensions
    must be either `1`, or the same as the corresponding `labels`
    dimension).
* <b>`metrics_collections`</b>: An optional list of collections that the metric
    value variable should be added to.
* <b>`updates_collections`</b>: An optional list of collections that the metric update
    ops should be added to.
* <b>`name`</b>: An optional variable_scope name.


#### Returns:

* <b>`count`</b>: A `Tensor` representing the current value of the metric.
* <b>`update_op`</b>: An operation that accumulates the metric from a batch of data.


#### Raises:

* <b>`ValueError`</b>: If `weights` is not `None` and its shape doesn't match `values`,
    or if either `metrics_collections` or `updates_collections` are not a list
    or tuple.