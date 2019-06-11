<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.summary.get_summary_description" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.summary.get_summary_description

Given a TensorSummary node_def, retrieve its SummaryDescription.

``` python
tf.compat.v1.summary.get_summary_description(node_def)
```



Defined in [`python/summary/summary.py`](/code/stable/tensorflow/python/summary/summary.py).

<!-- Placeholder for "Used in" -->

When a Summary op is instantiated, a SummaryDescription of associated
metadata is stored in its NodeDef. This method retrieves the description.

#### Args:


* <b>`node_def`</b>: the node_def_pb2.NodeDef of a TensorSummary op


#### Returns:

a summary_pb2.SummaryDescription



#### Raises:


* <b>`ValueError`</b>: if the node is not a summary op.



#### Eager Compatibility
Not compatible with eager execution. To write TensorBoard
summaries under eager execution, use `tf.contrib.summary` instead.

