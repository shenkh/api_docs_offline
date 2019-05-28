<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.graph_util" />
</div>

# Module: tf.graph_util



Defined in [`tensorflow/graph_util/__init__.py`](https://www.tensorflow.org/code/tensorflow/graph_util/__init__.py).

Helpers to manipulate a tensor graph in python.

## Functions

[`convert_variables_to_constants(...)`](../tf/graph_util/convert_variables_to_constants.md): Replaces all the variables in a graph with constants of the same values.

[`extract_sub_graph(...)`](../tf/graph_util/extract_sub_graph.md): Extract the subgraph that can reach any of the nodes in 'dest_nodes'.

[`must_run_on_cpu(...)`](../tf/graph_util/must_run_on_cpu.md): Returns True if the given node_def must run on CPU, otherwise False.

[`remove_training_nodes(...)`](../tf/graph_util/remove_training_nodes.md): Prunes out nodes that aren't needed for inference.

[`tensor_shape_from_node_def_name(...)`](../tf/graph_util/tensor_shape_from_node_def_name.md): Convenience function to get a shape from a NodeDef's input string.

