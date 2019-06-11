<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.summary.all_v2_summary_ops" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.summary.all_v2_summary_ops

Returns all V2-style summary ops defined in the current default graph.

``` python
tf.compat.v1.summary.all_v2_summary_ops()
```



Defined in [`python/ops/summary_ops_v2.py`](/code/stable/tensorflow/python/ops/summary_ops_v2.py).

<!-- Placeholder for "Used in" -->

This includes ops from TF 2.0 tf.summary and TF 1.x tf.contrib.summary (except
for `tf.contrib.summary.graph` and `tf.contrib.summary.import_event`), but
does *not* include TF 1.x tf.summary ops.

#### Returns:

List of summary ops, or None if called under eager execution.
