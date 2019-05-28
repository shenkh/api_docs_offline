<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.lite.convert_op_hints_to_stubs" />
</div>

# tf.contrib.lite.convert_op_hints_to_stubs

``` python
tf.contrib.lite.convert_op_hints_to_stubs(session)
```



Defined in [`tensorflow/contrib/lite/python/op_hint.py`](https://www.tensorflow.org/code/tensorflow/contrib/lite/python/op_hint.py).

Converts a graphdef with LiteOp hints into stub operations.

This is used to prepare for toco conversion of complex intrinsic usages.

#### Args:

* <b>`session`</b>: A TensorFlow session that contains the graph to convert.

#### Returns:

A new graphdef with all ops contained in OpHints being replaced by
a single op call with the right parameters.