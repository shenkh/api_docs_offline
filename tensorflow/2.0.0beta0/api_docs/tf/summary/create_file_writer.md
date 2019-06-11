<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary.create_file_writer" />
<meta itemprop="path" content="Stable" />
</div>

# tf.summary.create_file_writer

Creates a summary file writer for the given log directory.

### Aliases:

* `tf.compat.v2.summary.create_file_writer`
* `tf.summary.create_file_writer`

``` python
tf.summary.create_file_writer(
    logdir,
    max_queue=None,
    flush_millis=None,
    filename_suffix=None,
    name=None
)
```



Defined in [`python/ops/summary_ops_v2.py`](/code/stable/tensorflow/python/ops/summary_ops_v2.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`logdir`</b>: a string specifying the directory in which to write an event file.
* <b>`max_queue`</b>: the largest number of summaries to keep in a queue; will
 flush once the queue gets bigger than this. Defaults to 10.
* <b>`flush_millis`</b>: the largest interval between flushes. Defaults to 120,000.
* <b>`filename_suffix`</b>: optional suffix for the event file name. Defaults to `.v2`.
* <b>`name`</b>: a name for the op that creates the writer.


#### Returns:

A SummaryWriter object.
