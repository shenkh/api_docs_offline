<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distribute.has_distribution_strategy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.distribute.has_distribution_strategy

``` python
tf.contrib.distribute.has_distribution_strategy()
```



Defined in [`tensorflow/python/training/distribution_strategy_context.py`](/code/stable/tensorflow/python/training/distribution_strategy_context.py).

Return if there is a current non-default `DistributionStrategy`.

#### Returns:

True if inside a `with distribution_strategy.scope():`.