<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.make_view_from_scope" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.graph_editor.make_view_from_scope

### Aliases:

* `tf.contrib.graph_editor.make_view_from_scope`
* `tf.contrib.graph_editor.sgv_scope`

``` python
tf.contrib.graph_editor.make_view_from_scope(
    scope,
    graph
)
```



Defined in [`tensorflow/contrib/graph_editor/subgraph.py`](/code/stable/tensorflow/contrib/graph_editor/subgraph.py).

Make a subgraph from a name scope.

#### Args:

* <b>`scope`</b>: the name of the scope.
* <b>`graph`</b>: the <a href="../../../tf/Graph.md"><code>tf.Graph</code></a>.

#### Returns:

A subgraph view representing the given scope.