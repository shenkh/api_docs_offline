<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.train.MonitoredTrainingSession" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.train.MonitoredTrainingSession

Creates a `MonitoredSession` for training.

``` python
tf.compat.v1.train.MonitoredTrainingSession(
    master='',
    is_chief=True,
    checkpoint_dir=None,
    scaffold=None,
    hooks=None,
    chief_only_hooks=None,
    save_checkpoint_secs=USE_DEFAULT,
    save_summaries_steps=USE_DEFAULT,
    save_summaries_secs=USE_DEFAULT,
    config=None,
    stop_grace_period_secs=120,
    log_step_count_steps=100,
    max_wait_secs=7200,
    save_checkpoint_steps=USE_DEFAULT,
    summary_dir=None
)
```



Defined in [`python/training/monitored_session.py`](/code/stable/tensorflow/python/training/monitored_session.py).

<!-- Placeholder for "Used in" -->

For a chief, this utility sets proper session initializer/restorer. It also
creates hooks related to checkpoint and summary saving. For workers, this
utility sets proper session creator which waits for the chief to
initialize/restore. Please check <a href="../../../../tf/compat/v1/train/MonitoredSession.md"><code>tf.compat.v1.train.MonitoredSession</code></a> for
more
information.


#### Args:


* <b>`master`</b>: `String` the TensorFlow master to use.
* <b>`is_chief`</b>: If `True`, it will take care of initialization and recovery the
  underlying TensorFlow session. If `False`, it will wait on a chief to
  initialize or recover the TensorFlow session.
* <b>`checkpoint_dir`</b>: A string.  Optional path to a directory where to restore
  variables.
* <b>`scaffold`</b>: A `Scaffold` used for gathering or building supportive ops. If not
  specified, a default one is created. It's used to finalize the graph.
* <b>`hooks`</b>: Optional list of `SessionRunHook` objects.
* <b>`chief_only_hooks`</b>: list of `SessionRunHook` objects. Activate these hooks if
  `is_chief==True`, ignore otherwise.
* <b>`save_checkpoint_secs`</b>: The frequency, in seconds, that a checkpoint is saved
  using a default checkpoint saver. If both `save_checkpoint_steps` and
  `save_checkpoint_secs` are set to `None`, then the default checkpoint
  saver isn't used. If both are provided, then only `save_checkpoint_secs`
  is used. Default 600.
* <b>`save_summaries_steps`</b>: The frequency, in number of global steps, that the
  summaries are written to disk using a default summary saver. If both
  `save_summaries_steps` and `save_summaries_secs` are set to `None`, then
  the default summary saver isn't used. Default 100.
* <b>`save_summaries_secs`</b>: The frequency, in secs, that the summaries are written
  to disk using a default summary saver.  If both `save_summaries_steps` and
  `save_summaries_secs` are set to `None`, then the default summary saver
  isn't used. Default not enabled.
* <b>`config`</b>: an instance of <a href="../../../../tf/compat/v1/ConfigProto.md"><code>tf.compat.v1.ConfigProto</code></a> proto used to configure
  the session. It's the `config` argument of constructor of
  <a href="../../../../tf/compat/v1/Session.md"><code>tf.compat.v1.Session</code></a>.
* <b>`stop_grace_period_secs`</b>: Number of seconds given to threads to stop after
  `close()` has been called.
* <b>`log_step_count_steps`</b>: The frequency, in number of global steps, that the
  global step/sec is logged.
* <b>`max_wait_secs`</b>: Maximum time workers should wait for the session to become
  available. This should be kept relatively short to help detect incorrect
  code, but sometimes may need to be increased if the chief takes a while to
  start up.
* <b>`save_checkpoint_steps`</b>: The frequency, in number of global steps, that a
  checkpoint is saved using a default checkpoint saver. If both
  `save_checkpoint_steps` and `save_checkpoint_secs` are set to `None`, then
  the default checkpoint saver isn't used. If both are provided, then only
  `save_checkpoint_secs` is used. Default not enabled.
* <b>`summary_dir`</b>: A string.  Optional path to a directory where to save
  summaries. If None, checkpoint_dir is used instead.


#### Returns:

A `MonitoredSession` object.
