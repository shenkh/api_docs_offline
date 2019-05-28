<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.add_to_collection" />
</div>

# tf.add_to_collection

``` python
tf.add_to_collection(
    name,
    value
)
```



Defined in [`tensorflow/python/framework/ops.py`](https://www.tensorflow.org/code/tensorflow/python/framework/ops.py).

See the guide: [Building Graphs > Graph collections](../../../api_guides/python/framework.md#Graph_collections)

Wrapper for `Graph.add_to_collection()` using the default graph.

See <a href="../tf/Graph.md#add_to_collection"><code>tf.Graph.add_to_collection</code></a>
for more details.

#### Args:

* <b>`name`</b>: The key for the collection. For example, the `GraphKeys` class
    contains many standard names for collections.
* <b>`value`</b>: The value to add to the collection.



#### Eager Compatibility
Collections are only supported in eager when variables are created inside an
EagerVariableStore (e.g. as part of a layer or template).

