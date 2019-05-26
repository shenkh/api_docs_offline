<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.opt.ElasticAverageCustomGetter" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.contrib.opt.ElasticAverageCustomGetter

## Class `ElasticAverageCustomGetter`





Defined in [`tensorflow/contrib/opt/python/training/elastic_average_optimizer.py`](/code/stable/tensorflow/contrib/opt/python/training/elastic_average_optimizer.py).

Custom_getter class is used to do:
1. Change trainable variables to local collection and place them at worker
  device
2. Generate global variables(global center variables)
3. Generate local variables(local center variables) which record the global
  variables and place them at worker device
  Notice that the class should be used with tf.replica_device_setter,
  so that the global center variables and global step variable can be placed
  at ps device. Besides, use 'tf.get_variable' instead of 'tf.Variable' to
  use this custom getter.

For example,
ea_custom_getter = ElasticAverageCustomGetter(worker_device)
with tf.device(
  tf.train.replica_device_setter(
    worker_device=worker_device,
    ps_device="/job:ps",
    cluster=cluster)),
  tf.variable_scope('',custom_getter=ea_custom_getter):
  ...
  create your model here
  ...
  with tf.device(worker_device):
    opt = tf.train.MomentumOptimizer(...)
    optimizer = ElasticAverageOptimizer(
          opt,
          num_worker=2,
          moving_rate=0.01, # or use default value
          communication_period=20,
          ea_custom_getter=ea_custom_getter)
    ...
    train_op = optimizer.apply_gradients(
      grads_vars,
      global_step=global_step)
  ...
  hooks = [optimizer.make_session_run_hook(is_chief, task_index)]
  ...
  with tf.train.MonitoredTrainingSession(master=server.target,
                                         is_chief=is_chief,
                                         checkpoint_dir=("...),
                                         save_checkpoint_secs=600,
                                         hooks=hooks) as mon_sess:

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(worker_device)
```

Create a new `ElasticAverageCustomGetter`.

#### Args:

* <b>`worker_device`</b>: String.  Name of the `worker` job.



## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    getter,
    name,
    trainable,
    collections,
    *args,
    **kwargs
)
```

Call self as a function.



