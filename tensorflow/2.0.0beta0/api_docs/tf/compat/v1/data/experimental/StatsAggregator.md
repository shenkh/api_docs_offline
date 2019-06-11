<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.data.experimental.StatsAggregator" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get_summary"/>
</div>

# tf.compat.v1.data.experimental.StatsAggregator

## Class `StatsAggregator`

A stateful resource that aggregates statistics from one or more iterators.





Defined in [`python/data/experimental/ops/stats_aggregator.py`](/code/stable/tensorflow/python/data/experimental/ops/stats_aggregator.py).

<!-- Placeholder for "Used in" -->

To record statistics, use one of the custom transformation functions defined
in this module when defining your <a href="../../../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a>. All statistics will be
aggregated by the `StatsAggregator` that is associated with a particular
iterator (see below). For example, to record the latency of producing each
element by iterating over a dataset:

```python
dataset = ...
dataset = dataset.apply(tf.data.experimental.latency_stats("total_bytes"))
```

To associate a `StatsAggregator` with a <a href="../../../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> object, use
the following pattern:

```python
aggregator = tf.data.experimental.StatsAggregator()
dataset = ...

# Apply `StatsOptions` to associate `dataset` with `aggregator`.
options = tf.data.Options()
options.experimental_stats.aggregator = aggregator
dataset = dataset.with_options(options)
```

To get a protocol buffer summary of the currently aggregated statistics,
use the `StatsAggregator.get_summary()` tensor. The easiest way to do this
is to add the returned tensor to the `tf.GraphKeys.SUMMARIES` collection,
so that the summaries will be included with any existing summaries.

```python
aggregator = tf.data.experimental.StatsAggregator()
# ...
stats_summary = aggregator.get_summary()
tf.compat.v1.add_to_collection(tf.GraphKeys.SUMMARIES, stats_summary)
```

Note: This interface is experimental and expected to change. In particular,
we expect to add other implementations of `StatsAggregator` that provide
different ways of exporting statistics, and add more types of statistics.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__()
```

Creates a `StatsAggregator`.




## Methods

<h3 id="get_summary"><code>get_summary</code></h3>

``` python
get_summary()
```

Returns a string <a href="../../../../../tf/Tensor.md"><code>tf.Tensor</code></a> that summarizes the aggregated statistics.

The returned tensor will contain a serialized <a href="../../../../../tf/compat/v1/Summary.md"><code>tf.compat.v1.summary.Summary</code></a>
protocol
buffer, which can be used with the standard TensorBoard logging facilities.

#### Returns:

A scalar string <a href="../../../../../tf/Tensor.md"><code>tf.Tensor</code></a> that summarizes the aggregated statistics.




