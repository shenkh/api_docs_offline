<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary.flush" />
<meta itemprop="path" content="Stable" />
</div>

# tf.summary.flush

``` python
tf.summary.flush(
    writer=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/summary_ops_v2.py`](/code/stable/tensorflow/python/ops/summary_ops_v2.py).

Forces summary writer to send any buffered data to storage.

This operation blocks until that finishes.

#### Args:

* <b>`writer`</b>: The <a href="../../tf/summary/SummaryWriter.md"><code>tf.summary.SummaryWriter</code></a> resource to flush.
    The thread default will be used if this parameter is None.
    Otherwise a <a href="../../tf/no_op.md"><code>tf.no_op</code></a> is returned.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The created <a href="../../tf/Operation.md"><code>tf.Operation</code></a>.