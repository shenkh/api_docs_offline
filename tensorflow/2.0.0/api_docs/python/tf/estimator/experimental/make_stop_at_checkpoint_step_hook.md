<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.experimental.make_stop_at_checkpoint_step_hook" />
<meta itemprop="path" content="Stable" />
</div>

# tf.estimator.experimental.make_stop_at_checkpoint_step_hook

``` python
tf.estimator.experimental.make_stop_at_checkpoint_step_hook(
    estimator,
    last_step,
    wait_after_file_check_secs=30
)
```

Creates a proper StopAtCheckpointStepHook based on chief status.