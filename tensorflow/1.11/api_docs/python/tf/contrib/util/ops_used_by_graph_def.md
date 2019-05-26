<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.util.ops_used_by_graph_def" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.util.ops_used_by_graph_def

``` python
tf.contrib.util.ops_used_by_graph_def(graph_def)
```



Defined in [`tensorflow/python/framework/meta_graph.py`](https://www.tensorflow.org/code/tensorflow/python/framework/meta_graph.py).

Collect the list of ops used by a graph.

Does not validate that the ops are all registered.

#### Args:

* <b>`graph_def`</b>: A `GraphDef` proto, as from `graph.as_graph_def()`.


#### Returns:

A list of strings, each naming an op used by the graph.