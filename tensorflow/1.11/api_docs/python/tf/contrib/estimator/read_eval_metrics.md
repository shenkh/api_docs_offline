<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.estimator.read_eval_metrics" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.estimator.read_eval_metrics

``` python
tf.contrib.estimator.read_eval_metrics(eval_dir)
```



Defined in [`tensorflow/contrib/estimator/python/estimator/early_stopping.py`](https://www.tensorflow.org/code/tensorflow/contrib/estimator/python/estimator/early_stopping.py).

Helper to read eval metrics from eval summary files.

#### Args:

* <b>`eval_dir`</b>: Directory containing summary files with eval metrics.


#### Returns:

A `dict` with global steps mapping to `dict` of metric names and values.