<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.latency_stats" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.latency_stats

Records the latency of producing each element of the input dataset.

### Aliases:

* `tf.compat.v1.data.experimental.latency_stats`
* `tf.compat.v2.data.experimental.latency_stats`
* `tf.data.experimental.latency_stats`

``` python
tf.data.experimental.latency_stats(tag)
```



Defined in [`python/data/experimental/ops/stats_ops.py`](/code/stable/tensorflow/python/data/experimental/ops/stats_ops.py).

<!-- Placeholder for "Used in" -->

To consume the statistics, associate a `StatsAggregator` with the output
dataset.

#### Args:


* <b>`tag`</b>: String. All statistics recorded by the returned transformation will
  be associated with the given `tag`.


#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.
