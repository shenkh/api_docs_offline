<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.filter_ts" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.graph_editor.filter_ts

``` python
tf.contrib.graph_editor.filter_ts(
    ops,
    positive_filter
)
```



Defined in [`tensorflow/contrib/graph_editor/select.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/select.py).

See the guide: [Graph Editor (contrib) > Module: select](../../../../../api_guides/python/contrib.graph_editor.md#Module_select)

Get all the tensors which are input or output of an op in ops.

#### Args:

* <b>`ops`</b>: an object convertible to a list of <a href="../../../tf/Operation.md"><code>tf.Operation</code></a>.
* <b>`positive_filter`</b>: a function deciding whether to keep a tensor or not.
    If `True`, all the tensors are returned.

#### Returns:

A list of <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>.

#### Raises:

* <b>`TypeError`</b>: if ops cannot be converted to a list of <a href="../../../tf/Operation.md"><code>tf.Operation</code></a>.