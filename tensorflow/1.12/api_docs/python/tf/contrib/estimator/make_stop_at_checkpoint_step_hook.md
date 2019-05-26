<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.estimator.make_stop_at_checkpoint_step_hook" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.estimator.make_stop_at_checkpoint_step_hook

``` python
tf.contrib.estimator.make_stop_at_checkpoint_step_hook(
    estimator,
    last_step,
    wait_after_file_check_secs=30
)
```



Defined in [`tensorflow/contrib/estimator/python/estimator/hooks.py`](/code/stable/tensorflow/contrib/estimator/python/estimator/hooks.py).

Creates a proper StopAtCheckpointStepHook based on chief status.