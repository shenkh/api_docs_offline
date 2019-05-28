<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.make_view_from_scope" />
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



Defined in [`tensorflow/contrib/graph_editor/subgraph.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/subgraph.py).

See the guides: [Graph Editor (contrib) > Module: subgraph](../../../../../api_guides/python/contrib.graph_editor.md#Module_subgraph), [Graph Editor (contrib) > Useful aliases](../../../../../api_guides/python/contrib.graph_editor.md#Useful_aliases)

Make a subgraph from a name scope.

#### Args:

* <b>`scope`</b>: the name of the scope.
* <b>`graph`</b>: the <a href="../../../tf/Graph.md"><code>tf.Graph</code></a>.

#### Returns:

A subgraph view representing the given scope.