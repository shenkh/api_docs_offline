<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.distribute.get_strategy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.distribute.get_strategy

Returns the current <a href="../../tf/distribute/Strategy.md"><code>tf.distribute.Strategy</code></a> object.

### Aliases:

* `tf.compat.v1.distribute.get_strategy`
* `tf.compat.v2.distribute.get_strategy`
* `tf.distribute.get_strategy`

``` python
tf.distribute.get_strategy()
```



Defined in [`python/distribute/distribution_strategy_context.py`](/code/stable/tensorflow/python/distribute/distribution_strategy_context.py).

<!-- Placeholder for "Used in" -->

Typically only used in a cross-replica context:

```
if tf.distribute.in_cross_replica_context():
  strategy = tf.distribute.get_strategy()
  ...
```

#### Returns:

A <a href="../../tf/distribute/Strategy.md"><code>tf.distribute.Strategy</code></a> object. Inside a `with strategy.scope()` block,
it returns `strategy`, otherwise it returns the default (single-replica)
<a href="../../tf/distribute/Strategy.md"><code>tf.distribute.Strategy</code></a> object.
