<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.fuse_op" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.framework.fuse_op

``` python
tf.contrib.framework.fuse_op(
    graph_def,
    input_nodes,
    output_nodes,
    output_dtypes,
    output_quantized,
    op_name,
    op_type
)
```



Defined in [`tensorflow/contrib/framework/python/framework/graph_util.py`](/code/stable/tensorflow/contrib/framework/python/framework/graph_util.py).

Fuse subgraph between input_nodes and output_nodes into a single custom op.

#### Args:

* <b>`graph_def`</b>: A graph_pb2.GraphDef proto.
* <b>`input_nodes`</b>: input nodes to the subgraph to be fused.
* <b>`output_nodes`</b>: output nodes to the subgraph to be fused.
* <b>`output_dtypes`</b>: A list of output datatypes for the custom op
* <b>`output_quantized`</b>: A boolean flag that indicates if output is quantized
* <b>`op_name`</b>: fused op name.
* <b>`op_type`</b>: fused op type.

#### Returns:

The GraphDef of the new graph.


#### Raises:

* <b>`TypeError`</b>: If 'graph_def' is not a graph_pb2.GraphDef proto.