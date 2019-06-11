<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.distribute.in_cross_replica_context" />
<meta itemprop="path" content="Stable" />
</div>

# tf.distribute.in_cross_replica_context

Returns True if in a cross-replica context.

### Aliases:

* `tf.compat.v1.distribute.in_cross_replica_context`
* `tf.compat.v2.distribute.in_cross_replica_context`
* `tf.distribute.in_cross_replica_context`

``` python
tf.distribute.in_cross_replica_context()
```



Defined in [`python/distribute/distribution_strategy_context.py`](/code/stable/tensorflow/python/distribute/distribution_strategy_context.py).

<!-- Placeholder for "Used in" -->

See <a href="../../tf/distribute/get_replica_context.md"><code>tf.distribute.get_replica_context</code></a> for details.

#### Returns:

True if in a cross-replica context (`get_replica_context()` returns
`None`), or False if in a replica context (`get_replica_context()` returns
non-`None`).
