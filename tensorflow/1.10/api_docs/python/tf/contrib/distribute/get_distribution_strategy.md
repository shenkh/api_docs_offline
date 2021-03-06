<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distribute.get_distribution_strategy" />
</div>

# tf.contrib.distribute.get_distribution_strategy

``` python
tf.contrib.distribute.get_distribution_strategy()
```



Defined in [`tensorflow/python/training/distribute.py`](https://www.tensorflow.org/code/tensorflow/python/training/distribute.py).

Returns the current `DistributionStrategy` object.

Prefer to use `get_tower_context()` or `get_cross_tower_context()`
instead when possible.

#### Returns:

A `DistributionStrategy` object. Inside a
`with distribution_strategy.scope()` block, it returns
`distribution_strategy`, otherwise it returns the default
(single-tower) `DistributionStrategy` object.