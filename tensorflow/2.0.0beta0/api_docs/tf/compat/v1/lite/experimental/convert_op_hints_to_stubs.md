<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.lite.experimental.convert_op_hints_to_stubs" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.lite.experimental.convert_op_hints_to_stubs

Converts a graphdef with LiteOp hints into stub operations.

``` python
tf.compat.v1.lite.experimental.convert_op_hints_to_stubs(
    session=None,
    graph_def=None,
    write_callback=(lambda graph_def, comments: None)
)
```



Defined in [`lite/python/op_hint.py`](/code/stable/tensorflow/lite/python/op_hint.py).

<!-- Placeholder for "Used in" -->

This is used to prepare for toco conversion of complex intrinsic usages.
Note: only one of session or graph_def should be used, not both.

#### Args:


* <b>`session`</b>: A TensorFlow session that contains the graph to convert.
* <b>`graph_def`</b>: A graph def that we should convert.
* <b>`write_callback`</b>: A function pointer that can be used to write intermediate
  steps of graph transformation (optional).

#### Returns:

A new graphdef with all ops contained in OpHints being replaced by
a single op call with the right parameters.


#### Raises:


* <b>`ValueError`</b>: If both session and graph_def are provided.