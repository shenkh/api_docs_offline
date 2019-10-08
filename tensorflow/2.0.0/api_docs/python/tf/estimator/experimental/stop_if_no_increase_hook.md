<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.experimental.stop_if_no_increase_hook" />
<meta itemprop="path" content="Stable" />
</div>

# tf.estimator.experimental.stop_if_no_increase_hook

``` python
tf.estimator.experimental.stop_if_no_increase_hook(
    estimator,
    metric_name,
    max_steps_without_increase,
    eval_dir=None,
    min_steps=0,
    run_every_secs=60,
    run_every_steps=None
)
```

Creates hook to stop if metric does not increase within given max steps.

Usage example:

```python
estimator = ...
# Hook to stop training if accuracy does not increase in over 100000 steps.
hook = early_stopping.stop_if_no_increase_hook(estimator, "accuracy", 100000)
train_spec = tf.estimator.TrainSpec(..., hooks=[hook])
tf.estimator.train_and_evaluate(estimator, train_spec, ...)
```

Caveat: Current implementation supports early-stopping both training and
evaluation in local mode. In distributed mode, training can be stopped but
evaluation (where it's a separate job) will indefinitely wait for new model
checkpoints to evaluate, so you will need other means to detect and stop it.
Early-stopping evaluation in distributed mode requires changes in
`train_and_evaluate` API and will be addressed in a future revision.

#### Args:

* <b>`estimator`</b>: A <a href="../../../tf/estimator/Estimator.md"><code>tf.estimator.Estimator</code></a> instance.
* <b>`metric_name`</b>: `str`, metric to track. "loss", "accuracy", etc.
* <b>`max_steps_without_increase`</b>: `int`, maximum number of training steps with no
    increase in the given metric.
* <b>`eval_dir`</b>: If set, directory containing summary files with eval metrics. By
    default, `estimator.eval_dir()` will be used.
* <b>`min_steps`</b>: `int`, stop is never requested if global step is less than this
    value. Defaults to 0.
* <b>`run_every_secs`</b>: If specified, calls `should_stop_fn` at an interval of
    `run_every_secs` seconds. Defaults to 60 seconds. Either this or
    `run_every_steps` must be set.
* <b>`run_every_steps`</b>: If specified, calls `should_stop_fn` every
    `run_every_steps` steps. Either this or `run_every_secs` must be set.


#### Returns:

An early-stopping hook of type `SessionRunHook` that periodically checks
if the given metric shows no increase over given maximum number of
training steps, and initiates early stopping if true.