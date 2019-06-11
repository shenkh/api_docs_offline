<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.get_seed" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.get_seed

Returns the local seeds an operation should use given an op-specific seed.

### Aliases:

* `tf.compat.v1.get_seed`
* `tf.compat.v1.random.get_seed`

``` python
tf.compat.v1.get_seed(op_seed)
```



Defined in [`python/framework/random_seed.py`](/code/stable/tensorflow/python/framework/random_seed.py).

<!-- Placeholder for "Used in" -->

Given operation-specific seed, `op_seed`, this helper function returns two
seeds derived from graph-level and op-level seeds. Many random operations
internally use the two seeds to allow user to change the seed globally for a
graph, or for only specific operations.

For details on how the graph-level seed interacts with op seeds, see
<a href="../../../tf/compat/v1/set_random_seed.md"><code>tf.compat.v1.random.set_random_seed</code></a>.

#### Args:


* <b>`op_seed`</b>: integer.


#### Returns:

A tuple of two integers that should be used for the local seed of this
operation.
