<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.summary.initialize" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.summary.initialize

``` python
tf.contrib.summary.initialize(
    graph=None,
    session=None
)
```



Defined in [`tensorflow/python/ops/summary_ops_v2.py`](https://www.tensorflow.org/code/tensorflow/python/ops/summary_ops_v2.py).

Initializes summary writing for graph execution mode.

This helper method provides a higher-level alternative to using
<a href="../../../tf/contrib/summary/summary_writer_initializer_op.md"><code>tf.contrib.summary.summary_writer_initializer_op</code></a> and
<a href="../../../tf/contrib/summary/graph.md"><code>tf.contrib.summary.graph</code></a>.

Most users will also want to call <a href="../../../tf/train/create_global_step.md"><code>tf.train.create_global_step</code></a>
which can happen before or after this function is called.

#### Args:

* <b>`graph`</b>: A <a href="../../../tf/Graph.md"><code>tf.Graph</code></a> or <a href="../../../tf/GraphDef.md"><code>tf.GraphDef</code></a> to output to the writer.
    This function will not write the default graph by default. When
    writing to an event log file, the associated step will be zero.
* <b>`session`</b>: So this method can call <a href="../../../tf/InteractiveSession.md#run"><code>tf.Session.run</code></a>. This defaults
    to <a href="../../../tf/get_default_session.md"><code>tf.get_default_session</code></a>.


#### Raises:

* <b>`RuntimeError`</b>: If  the current thread has no default
    <a href="../../../tf/contrib/summary/SummaryWriter.md"><code>tf.contrib.summary.SummaryWriter</code></a>.
* <b>`ValueError`</b>: If session wasn't passed and no default session.