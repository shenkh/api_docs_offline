<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.summary.flush" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.summary.flush

``` python
tf.contrib.summary.flush(
    writer=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/summary_ops_v2.py`](https://www.tensorflow.org/code/tensorflow/python/ops/summary_ops_v2.py).

Forces summary writer to send any buffered data to storage.

This operation blocks until that finishes.

#### Args:

* <b>`writer`</b>: The <a href="../../../tf/contrib/summary/SummaryWriter.md"><code>tf.contrib.summary.SummaryWriter</code></a> resource to flush.
    The thread default will be used if this parameter is None.
    Otherwise a <a href="../../../tf/no_op.md"><code>tf.no_op</code></a> is returned.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The created <a href="../../../tf/Operation.md"><code>tf.Operation</code></a>.