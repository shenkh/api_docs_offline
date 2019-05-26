<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.get_consuming_ops" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.graph_editor.get_consuming_ops

``` python
tf.contrib.graph_editor.get_consuming_ops(ts)
```



Defined in [`tensorflow/contrib/graph_editor/util.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/util.py).

See the guide: [Graph Editor (contrib) > Module: util](../../../../../api_guides/python/contrib.graph_editor.md#Module_util)

Return all the consuming ops of the tensors in ts.

#### Args:

* <b>`ts`</b>: a list of <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>

#### Returns:

A list of all the consuming <a href="../../../tf/Operation.md"><code>tf.Operation</code></a> of the tensors in `ts`.

#### Raises:

* <b>`TypeError`</b>: if ts cannot be converted to a list of <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>.