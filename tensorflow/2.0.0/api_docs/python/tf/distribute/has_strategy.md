<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.distribute.has_strategy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.distribute.has_strategy

``` python
tf.distribute.has_strategy()
```



Defined in [`tensorflow/python/distribute/distribution_strategy_context.py`](/code/stable/tensorflow/python/distribute/distribution_strategy_context.py).

Return if there is a current non-default <a href="../../tf/distribute/Strategy.md"><code>tf.distribute.Strategy</code></a>.

```
assert not tf.distribute.has_strategy()
with strategy.scope():
  assert tf.distribute.has_strategy()
```

#### Returns:

True if inside a `with strategy.scope():`.