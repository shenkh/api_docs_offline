<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.filter_ops" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.graph_editor.filter_ops

``` python
tf.contrib.graph_editor.filter_ops(
    ops,
    positive_filter
)
```



Defined in [`tensorflow/contrib/graph_editor/select.py`](/code/stable/tensorflow/contrib/graph_editor/select.py).

Get the ops passing the given filter.

#### Args:

* <b>`ops`</b>: an object convertible to a list of tf.Operation.
* <b>`positive_filter`</b>: a function deciding where to keep an operation or not.
    If True, all the operations are returned.

#### Returns:

A list of selected tf.Operation.

#### Raises:

* <b>`TypeError`</b>: if ops cannot be converted to a list of tf.Operation.