<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.Options" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="experimental_autotune"/>
<meta itemprop="property" content="experimental_filter_fusion"/>
<meta itemprop="property" content="experimental_hoist_random_uniform"/>
<meta itemprop="property" content="experimental_latency_all_edges"/>
<meta itemprop="property" content="experimental_map_and_batch_fusion"/>
<meta itemprop="property" content="experimental_map_and_filter_fusion"/>
<meta itemprop="property" content="experimental_map_fusion"/>
<meta itemprop="property" content="experimental_map_parallelization"/>
<meta itemprop="property" content="experimental_map_vectorization"/>
<meta itemprop="property" content="experimental_noop_elimination"/>
<meta itemprop="property" content="experimental_shuffle_and_repeat_fusion"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__ne__"/>
<meta itemprop="property" content="merge"/>
</div>

# tf.data.Options

## Class `Options`





Defined in [`tensorflow/python/data/ops/dataset_ops.py`](/code/stable/tensorflow/python/data/ops/dataset_ops.py).

Represents options for tf.data.Dataset.

An `Options` object can be for instance used to control which static
optimizations to apply or whether to use performance modeling to dynamically
tune the parallelism of operations such as <a href="../../tf/data/Dataset.md#map"><code>tf.data.Dataset.map</code></a> or
<a href="../../tf/data/Dataset.md#interleave"><code>tf.data.Dataset.interleave</code></a>.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__()
```

Initialize self.  See help(type(self)) for accurate signature.



## Properties

<h3 id="experimental_autotune"><code>experimental_autotune</code></h3>

Whether to dynamically adjust the values of tunable parameters (e.g. degrees of parallelism).

<h3 id="experimental_filter_fusion"><code>experimental_filter_fusion</code></h3>

Whether to fuse filter transformations.

<h3 id="experimental_hoist_random_uniform"><code>experimental_hoist_random_uniform</code></h3>

Whether to hoist `tf.random_uniform()` ops out of map transformations.

<h3 id="experimental_latency_all_edges"><code>experimental_latency_all_edges</code></h3>

Whether to add latency measurements on all edges.

<h3 id="experimental_map_and_batch_fusion"><code>experimental_map_and_batch_fusion</code></h3>

Whether to fuse map and batch transformations.

<h3 id="experimental_map_and_filter_fusion"><code>experimental_map_and_filter_fusion</code></h3>

Whether to fuse map and filter transformations.

<h3 id="experimental_map_fusion"><code>experimental_map_fusion</code></h3>

Whether to fuse map transformations.

<h3 id="experimental_map_parallelization"><code>experimental_map_parallelization</code></h3>

Whether to parallelize stateless map transformations.

<h3 id="experimental_map_vectorization"><code>experimental_map_vectorization</code></h3>

Whether to vectorize map transformations.

<h3 id="experimental_noop_elimination"><code>experimental_noop_elimination</code></h3>

Whether to eliminate no-op transformations.

<h3 id="experimental_shuffle_and_repeat_fusion"><code>experimental_shuffle_and_repeat_fusion</code></h3>

Whether to fuse shuffle and repeat transformations.



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



