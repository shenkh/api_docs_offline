<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distribute.has_distribution_strategy" />
</div>

# tf.contrib.distribute.has_distribution_strategy

``` python
tf.contrib.distribute.has_distribution_strategy()
```



Defined in [`tensorflow/python/training/distribute.py`](https://www.tensorflow.org/code/tensorflow/python/training/distribute.py).

Return if there is a current non-default `DistributionStrategy`.

#### Returns:

True if inside a `with distribution_strategy.scope():`.