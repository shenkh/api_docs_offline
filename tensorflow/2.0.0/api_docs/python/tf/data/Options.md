<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.Options" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="experimental_deterministic"/>
<meta itemprop="property" content="experimental_distribute"/>
<meta itemprop="property" content="experimental_optimization"/>
<meta itemprop="property" content="experimental_slack"/>
<meta itemprop="property" content="experimental_stats"/>
<meta itemprop="property" content="experimental_threading"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__ne__"/>
<meta itemprop="property" content="__setattr__"/>
<meta itemprop="property" content="merge"/>
</div>

# tf.data.Options

## Class `Options`





Defined in [`tensorflow/python/data/ops/dataset_ops.py`](/code/stable/tensorflow/python/data/ops/dataset_ops.py).

Represents options for tf.data.Dataset.

An `Options` object can be, for instance, used to control which static
optimizations to apply or whether to use performance modeling to dynamically
tune the parallelism of operations such as <a href="../../tf/data/Dataset.md#map"><code>tf.data.Dataset.map</code></a> or
<a href="../../tf/data/Dataset.md#interleave"><code>tf.data.Dataset.interleave</code></a>.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__()
```

Initialize self.  See help(type(self)) for accurate signature.



## Properties

<h3 id="experimental_deterministic"><code>experimental_deterministic</code></h3>

Whether the outputs need to be produced in deterministic order. If None, defaults to True.

<h3 id="experimental_distribute"><code>experimental_distribute</code></h3>

The distribution strategy options associated with the dataset. See <a href="../../tf/data/experimental/DistributeOptions.md"><code>tf.data.experimental.DistributeOptions</code></a> for more details.

<h3 id="experimental_optimization"><code>experimental_optimization</code></h3>

The optimization options associated with the dataset. See <a href="../../tf/data/experimental/OptimizationOptions.md"><code>tf.data.experimental.OptimizationOptions</code></a> for more details.

<h3 id="experimental_slack"><code>experimental_slack</code></h3>

Whether to introduce 'slack' in the last `prefetch` of the input pipeline, if it exists. This may reduce CPU contention with accelerator host-side activity at the start of a step. The slack frequency is determined by the number of devices attached to this input pipeline. If None, defaults to False.

<h3 id="experimental_stats"><code>experimental_stats</code></h3>

The statistics options associated with the dataset. See <a href="../../tf/data/experimental/StatsOptions.md"><code>tf.data.experimental.StatsOptions</code></a> for more details.

<h3 id="experimental_threading"><code>experimental_threading</code></h3>

The threading options associated with the dataset. See <a href="../../tf/data/experimental/ThreadingOptions.md"><code>tf.data.experimental.ThreadingOptions</code></a> for more details.



## Methods

<h3 id="__eq__"><code>__eq__</code></h3>

``` python
__eq__(other)
```

Return self==value.

<h3 id="__ne__"><code>__ne__</code></h3>

``` python
__ne__(other)
```

Return self!=value.

<h3 id="__setattr__"><code>__setattr__</code></h3>

``` python
__setattr__(
    name,
    value
)
```

Implement setattr(self, name, value).

<h3 id="merge"><code>merge</code></h3>

``` python
merge(options)
```

Merges itself with the given <a href="../../tf/data/Options.md"><code>tf.data.Options</code></a>.

The given <a href="../../tf/data/Options.md"><code>tf.data.Options</code></a> can be merged as long as there does not exist an
attribute that is set to different values in `self` and `options`.

#### Args:

* <b>`options`</b>: a <a href="../../tf/data/Options.md"><code>tf.data.Options</code></a> to merge with


#### Raises:

* <b>`ValueError`</b>: if the given <a href="../../tf/data/Options.md"><code>tf.data.Options</code></a> cannot be merged


#### Returns:

New `tf.data.Options()` object which is the result of merging self with
the input <a href="../../tf/data/Options.md"><code>tf.data.Options</code></a>.



