<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.summary.import_event" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.summary.import_event

``` python
tf.contrib.summary.import_event(
    tensor,
    name=None
)
```



Defined in [`tensorflow/python/ops/summary_ops_v2.py`](/code/stable/tensorflow/python/ops/summary_ops_v2.py).

Writes a <a href="../../../tf/Event.md"><code>tf.Event</code></a> binary proto.

When using create_db_writer(), this can be used alongside
<a href="../../../tf/TFRecordReader.md"><code>tf.TFRecordReader</code></a> to load event logs into the database. Please
note that this is lower level than the other summary functions and
will ignore any conditions set by methods like
<a href="../../../tf/contrib/summary/should_record_summaries.md"><code>tf.contrib.summary.should_record_summaries</code></a>.

#### Args:

* <b>`tensor`</b>: A <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a> of type `string` containing a serialized
    <a href="../../../tf/Event.md"><code>tf.Event</code></a> proto.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The created <a href="../../../tf/Operation.md"><code>tf.Operation</code></a>.