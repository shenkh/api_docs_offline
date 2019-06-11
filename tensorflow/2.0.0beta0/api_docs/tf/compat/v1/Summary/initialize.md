<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.summary.initialize" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.summary.initialize

Initializes summary writing for graph execution mode.

``` python
tf.compat.v1.summary.initialize(
    graph=None,
    session=None
)
```



Defined in [`python/ops/summary_ops_v2.py`](/code/stable/tensorflow/python/ops/summary_ops_v2.py).

<!-- Placeholder for "Used in" -->

This operation is a no-op when executing eagerly.

This helper method provides a higher-level alternative to using
`tf.contrib.summary.summary_writer_initializer_op` and
`tf.contrib.summary.graph`.

Most users will also want to call <a href="../../../../tf/compat/v1/train/create_global_step.md"><code>tf.compat.v1.train.create_global_step</code></a>
which can happen before or after this function is called.

#### Args:


* <b>`graph`</b>: A <a href="../../../../tf/Graph.md"><code>tf.Graph</code></a> or <a href="../../../../tf/compat/v1/GraphDef.md"><code>tf.compat.v1.GraphDef</code></a> to output to the writer.
  This function will not write the default graph by default. When
  writing to an event log file, the associated step will be zero.
* <b>`session`</b>: So this method can call `tf.Session.run`. This defaults
  to <a href="../../../../tf/compat/v1/get_default_session.md"><code>tf.compat.v1.get_default_session</code></a>.


#### Raises:


* <b>`RuntimeError`</b>: If  the current thread has no default
  `tf.contrib.summary.SummaryWriter`.
* <b>`ValueError`</b>: If session wasn't passed and no default session.