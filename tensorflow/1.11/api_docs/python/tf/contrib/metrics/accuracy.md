<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.metrics.accuracy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.metrics.accuracy

``` python
tf.contrib.metrics.accuracy(
    predictions,
    labels,
    weights=None,
    name=None
)
```



Defined in [`tensorflow/contrib/metrics/python/metrics/classification.py`](https://www.tensorflow.org/code/tensorflow/contrib/metrics/python/metrics/classification.py).

See the guide: [Metrics (contrib) > Metric `Ops`](../../../../../api_guides/python/contrib.metrics.md#Metric_Ops_)

Computes the percentage of times that predictions matches labels.

#### Args:

* <b>`predictions`</b>: the predicted values, a `Tensor` whose dtype and shape
               matches 'labels'.
* <b>`labels`</b>: the ground truth values, a `Tensor` of any shape and
          bool, integer, or string dtype.
* <b>`weights`</b>: None or `Tensor` of float values to reweight the accuracy.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

Accuracy `Tensor`.


#### Raises:

* <b>`ValueError`</b>: if dtypes don't match or
              if dtype is not bool, integer, or string.