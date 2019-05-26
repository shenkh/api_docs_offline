<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.get_generating_ops" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.graph_editor.get_generating_ops

``` python
tf.contrib.graph_editor.get_generating_ops(ts)
```



Defined in [`tensorflow/contrib/graph_editor/util.py`](/code/stable/tensorflow/contrib/graph_editor/util.py).

Return all the generating ops of the tensors in `ts`.

#### Args:

* <b>`ts`</b>: a list of <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>

#### Returns:

A list of all the generating <a href="../../../tf/Operation.md"><code>tf.Operation</code></a> of the tensors in `ts`.

#### Raises:

* <b>`TypeError`</b>: if `ts` cannot be converted to a list of <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>.