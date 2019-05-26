<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.make_view" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.graph_editor.make_view

### Aliases:

* `tf.contrib.graph_editor.make_view`
* `tf.contrib.graph_editor.sgv`

``` python
tf.contrib.graph_editor.make_view(
    *args,
    **kwargs
)
```



Defined in [`tensorflow/contrib/graph_editor/subgraph.py`](/code/stable/tensorflow/contrib/graph_editor/subgraph.py).

Create a SubGraphView from selected operations and passthrough tensors.

#### Args:

* <b>`*args`</b>: list of 1) regular expressions (compiled or not) or 2) (array of)
    <a href="../../../tf/Operation.md"><code>tf.Operation</code></a> 3) (array of) <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>. Those objects will be converted
    into a list of operations and a list of candidate for passthrough tensors.
* <b>`**kwargs`</b>: keyword graph is used 1) to check that the ops and ts are from
    the correct graph 2) for regular expression query

#### Returns:

A subgraph view.

#### Raises:

* <b>`TypeError`</b>: if the optional keyword argument graph is not a <a href="../../../tf/Graph.md"><code>tf.Graph</code></a>
    or if an argument in args is not an (array of) <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>
    or an (array of) <a href="../../../tf/Operation.md"><code>tf.Operation</code></a> or a string or a regular expression.
* <b>`ValueError`</b>: if one of the keyword arguments is unexpected.