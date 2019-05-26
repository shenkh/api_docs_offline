<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.set_stats_aggregator" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.set_stats_aggregator

``` python
tf.data.experimental.set_stats_aggregator(stats_aggregator)
```



Defined in [`tensorflow/python/data/experimental/ops/stats_ops.py`](/code/stable/tensorflow/python/data/experimental/ops/stats_ops.py).

Set the given `stats_aggregator` for aggregating the input dataset stats.

#### Args:

* <b>`stats_aggregator`</b>: A <a href="../../../tf/data/experimental/StatsAggregator.md"><code>tf.data.experimental.StatsAggregator</code></a> object.


#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.