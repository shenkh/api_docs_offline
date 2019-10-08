<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary.experimental.get_step" />
<meta itemprop="path" content="Stable" />
</div>

# tf.summary.experimental.get_step

``` python
tf.summary.experimental.get_step()
```



Defined in [`tensorflow/python/ops/summary_ops_v2.py`](/code/stable/tensorflow/python/ops/summary_ops_v2.py).

Returns the default summary step for the current thread.

#### Returns:

The step set by `tf.summary.experimental.set_step()` if one has been set,
otherwise None.