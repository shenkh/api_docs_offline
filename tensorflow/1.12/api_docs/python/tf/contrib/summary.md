<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.summary" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="absolute_import"/>
<meta itemprop="property" content="division"/>
<meta itemprop="property" content="print_function"/>
</div>

# Module: tf.contrib.summary



Defined in [`tensorflow/contrib/summary/summary.py`](/code/stable/tensorflow/contrib/summary/summary.py).

TensorFlow Summary API v2.

The operations in this package are safe to use with eager execution turned on or
off. It has a more flexible API that allows summaries to be written directly
from ops to places other than event log files, rather than propagating protos
from <a href="../../tf/summary/merge_all.md"><code>tf.summary.merge_all</code></a> to <a href="../../tf/summary/FileWriter.md"><code>tf.summary.FileWriter</code></a>.

To use with eager execution enabled, write your code as follows:

```python
global_step = tf.train.get_or_create_global_step()
summary_writer = tf.contrib.summary.create_file_writer(
    train_dir, flush_millis=10000)
with summary_writer.as_default(), tf.contrib.summary.always_record_summaries():
  # model code goes here
  # and in it call
  tf.contrib.summary.scalar("loss", my_loss)
  # In this case every call to tf.contrib.summary.scalar will generate a record
  # ...
```

To use it with graph execution, write your code as follows:

```python
global_step = tf.train.get_or_create_global_step()
summary_writer = tf.contrib.summary.create_file_writer(
    train_dir, flush_millis=10000)
with summary_writer.as_default(), tf.contrib.summary.always_record_summaries():
  # model definition code goes here
  # and in it call
  tf.contrib.summary.scalar("loss", my_loss)
  # In this case every call to tf.contrib.summary.scalar will generate an op,
  # note the need to run tf.contrib.summary.all_summary_ops() to make sure these
  # ops get executed.
  # ...
  train_op = ....

with tf.Session(...) as sess:
  tf.global_variables_initializer().run()
  tf.contrib.summary.initialize(graph=tf.get_default_graph())
  # ...
  while not_done_training:
    sess.run([train_op, tf.contrib.summary.all_summary_ops()])
    # ...
```

## Classes

[`class SummaryWriter`](../../tf/contrib/summary/SummaryWriter.md): Encapsulates a stateful summary writer resource.

## Functions

[`all_summary_ops(...)`](../../tf/contrib/summary/all_summary_ops.md): Graph-mode only. Returns all summary ops.

[`always_record_summaries(...)`](../../tf/contrib/summary/always_record_summaries.md): Sets the should_record_summaries Tensor to always true.

[`audio(...)`](../../tf/contrib/summary/audio.md): Writes an audio summary if possible.

[`create_db_writer(...)`](../../tf/contrib/summary/create_db_writer.md): Creates a summary database writer in the current context.

[`create_file_writer(...)`](../../tf/contrib/summary/create_file_writer.md): Creates a summary file writer in the current context under the given name.

[`create_summary_file_writer(...)`](../../tf/contrib/summary/create_summary_file_writer.md): Please use <a href="../../tf/contrib/summary/create_file_writer.md"><code>tf.contrib.summary.create_file_writer</code></a>.

[`eval_dir(...)`](../../tf/contrib/summary/eval_dir.md): Construct a logdir for an eval summary writer.

[`flush(...)`](../../tf/contrib/summary/flush.md): Forces summary writer to send any buffered data to storage.

[`generic(...)`](../../tf/contrib/summary/generic.md): Writes a tensor summary if possible.

[`graph(...)`](../../tf/contrib/summary/graph.md): Writes a TensorFlow graph to the summary interface.

[`histogram(...)`](../../tf/contrib/summary/histogram.md): Writes a histogram summary if possible.

[`image(...)`](../../tf/contrib/summary/image.md): Writes an image summary if possible.

[`import_event(...)`](../../tf/contrib/summary/import_event.md): Writes a <a href="../../tf/Event.md"><code>tf.Event</code></a> binary proto.

[`initialize(...)`](../../tf/contrib/summary/initialize.md): Initializes summary writing for graph execution mode.

[`never_record_summaries(...)`](../../tf/contrib/summary/never_record_summaries.md): Sets the should_record_summaries Tensor to always false.

[`record_summaries_every_n_global_steps(...)`](../../tf/contrib/summary/record_summaries_every_n_global_steps.md): Sets the should_record_summaries Tensor to true if global_step % n == 0.

[`scalar(...)`](../../tf/contrib/summary/scalar.md): Writes a scalar summary if possible.

[`should_record_summaries(...)`](../../tf/contrib/summary/should_record_summaries.md): Returns boolean Tensor which is true if summaries should be recorded.

[`summary_writer_initializer_op(...)`](../../tf/contrib/summary/summary_writer_initializer_op.md): Graph-mode only. Returns the list of ops to create all summary writers.

## Other Members

<h3 id="absolute_import"><code>absolute_import</code></h3>

<h3 id="division"><code>division</code></h3>

<h3 id="print_function"><code>print_function</code></h3>

