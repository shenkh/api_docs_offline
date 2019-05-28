<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.estimator.make_fisher_estimator" />
</div>

# tf.contrib.kfac.estimator.make_fisher_estimator

``` python
tf.contrib.kfac.estimator.make_fisher_estimator(
    placement_strategy=None,
    **kwargs
)
```



Defined in [`tensorflow/contrib/kfac/python/ops/estimator.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/estimator.py).

Creates Fisher estimator instances based on the placement strategy.

For example if the `placement_strategy` is 'round_robin' then
`FisherEstimatorRoundRobin` instance is returned.

#### Args:

* <b>`placement_strategy`</b>: `string`, Strategy to be used for placing covariance
    variables, covariance ops and inverse ops. Check
    `placement.FisherEstimatorRoundRobin` for a concrete example.
 **kwargs: Arguments to be passed into `FisherEstimator` class initializer.


#### Returns:

An instance of class which inherits from `FisherEstimator` and the mixin
which implements specific placement strategy. See,
`FisherEstimatorRoundRobin` which inherits from `FisherEstimator` and
`RoundRobinPlacementMixin`.


#### Raises:

* <b>`ValueError`</b>: If the `placement_strategy` is not equal to 'round_robin'.