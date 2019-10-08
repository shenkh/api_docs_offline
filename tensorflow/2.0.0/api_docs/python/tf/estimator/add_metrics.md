<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.add_metrics" />
<meta itemprop="path" content="Stable" />
</div>

# tf.estimator.add_metrics

``` python
tf.estimator.add_metrics(
    estimator,
    metric_fn
)
```

Creates a new <a href="../../tf/estimator/Estimator.md"><code>tf.estimator.Estimator</code></a> which has given metrics.

Example:

```python
  def my_auc(labels, predictions):
    auc_metric = tf.keras.metrics.AUC(name="my_auc")
    auc_metric.update_state(y_true=labels, y_pred=predictions['logistic'])
    return {'auc': auc_metric}

  estimator = tf.estimator.DNNClassifier(...)
  estimator = tf.estimator.add_metrics(estimator, my_auc)
  estimator.train(...)
  estimator.evaluate(...)
```
Example usage of custom metric which uses features:

```python
  def my_auc(labels, predictions, features):
    auc_metric = tf.keras.metrics.AUC(name="my_auc")
    auc_metric.update_state(y_true=labels, y_pred=predictions['logistic'],
                            sample_weight=features['weight'])
    return {'auc': auc_metric}

  estimator = tf.estimator.DNNClassifier(...)
  estimator = tf.estimator.add_metrics(estimator, my_auc)
  estimator.train(...)
  estimator.evaluate(...)
```

#### Args:

* <b>`estimator`</b>: A <a href="../../tf/estimator/Estimator.md"><code>tf.estimator.Estimator</code></a> object.
* <b>`metric_fn`</b>: A function which should obey the following signature:
    - Args: can only have following four arguments in any order:
      * predictions: Predictions `Tensor` or dict of `Tensor` created by given
        `estimator`.
      * features: Input `dict` of `Tensor` objects created by `input_fn` which
        is given to `estimator.evaluate` as an argument.
      * labels:  Labels `Tensor` or dict of `Tensor` created by `input_fn`
        which is given to `estimator.evaluate` as an argument.
      * config: config attribute of the `estimator`.
     - Returns:
       Dict of metric results keyed by name. Final metrics are a union of this
       and `estimator's` existing metrics. If there is a name conflict between
       this and `estimator`s existing metrics, this will override the existing
       one. The values of the dict are the results of calling a metric
       function, namely a `(metric_tensor, update_op)` tuple.


#### Returns:

A new <a href="../../tf/estimator/Estimator.md"><code>tf.estimator.Estimator</code></a> which has a union of original metrics with
  given ones.