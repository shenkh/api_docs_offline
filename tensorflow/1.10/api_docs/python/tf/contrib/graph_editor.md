<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor" />
</div>

# Module: tf.contrib.graph_editor



Defined in [`tensorflow/contrib/graph_editor/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/__init__.py).

TensorFlow Graph Editor.

See the <a href="../../../../api_guides/python/contrib.graph_editor.md">Graph Editor (contrib)</a> guide.

## Modules

[`edit`](../../tf/contrib/graph_editor/edit.md) module: Various function for graph editing.

[`reroute`](../../tf/contrib/graph_editor/reroute.md) module: Various function for graph rerouting.

[`select`](../../tf/contrib/graph_editor/select.md) module: Various ways of selecting operations and tensors in a graph.

[`subgraph`](../../tf/contrib/graph_editor/subgraph.md) module: SubGraphView: a subgraph view on an existing tf.Graph.

[`transform`](../../tf/contrib/graph_editor/transform.md) module: Class to transform an subgraph into another.

[`util`](../../tf/contrib/graph_editor/util.md) module: Utility functions for the graph_editor.

## Classes

[`class ControlOutputs`](../../tf/contrib/graph_editor/ControlOutputs.md): The control outputs topology.

[`class SubGraphView`](../../tf/contrib/graph_editor/SubGraphView.md): A subgraph view on an existing <a href="../../tf/Graph.md"><code>tf.Graph</code></a>.

[`class Transformer`](../../tf/contrib/graph_editor/Transformer.md): Transform a subgraph into another one.

[`class TransformerInfo`](../../tf/contrib/graph_editor/TransformerInfo.md): "Contains information about the result of a transform operation.

## Functions

[`add_control_inputs(...)`](../../tf/contrib/graph_editor/add_control_inputs.md): Add the control inputs cops to op.

[`assign_renamed_collections_handler(...)`](../../tf/contrib/graph_editor/assign_renamed_collections_handler.md): Add the transformed elem to the (renamed) collections of elem.

[`bypass(...)`](../../tf/contrib/graph_editor/bypass.md): Bypass the given subgraph by connecting its inputs to its outputs.

[`can_be_regex(...)`](../../tf/contrib/graph_editor/can_be_regex.md): Return True if obj can be turned into a regular expression.

[`check_cios(...)`](../../tf/contrib/graph_editor/check_cios.md): Do various check on control_inputs and control_outputs.

[`compute_boundary_ts(...)`](../../tf/contrib/graph_editor/compute_boundary_ts.md): Compute the tensors at the boundary of a set of ops.

[`connect(...)`](../../tf/contrib/graph_editor/connect.md): Connect the outputs of sgv0 to the inputs of sgv1.

[`copy(...)`](../../tf/contrib/graph_editor/copy.md): Copy a subgraph.

[`copy_op_handler(...)`](../../tf/contrib/graph_editor/copy_op_handler.md): Copy a <a href="../../tf/Operation.md"><code>tf.Operation</code></a>.

[`copy_with_input_replacements(...)`](../../tf/contrib/graph_editor/copy_with_input_replacements.md): Copy a subgraph, replacing some of its inputs.

[`detach(...)`](../../tf/contrib/graph_editor/detach.md): Detach both the inputs and the outputs of a subgraph view.

[`detach_control_inputs(...)`](../../tf/contrib/graph_editor/detach_control_inputs.md): Detach all the external control inputs of the subgraph sgv.

[`detach_control_outputs(...)`](../../tf/contrib/graph_editor/detach_control_outputs.md): Detach all the external control outputs of the subgraph sgv.

[`detach_inputs(...)`](../../tf/contrib/graph_editor/detach_inputs.md): Detach the inputs of a subgraph view.

[`detach_outputs(...)`](../../tf/contrib/graph_editor/detach_outputs.md): Detach the output of a subgraph view.

[`filter_ops(...)`](../../tf/contrib/graph_editor/filter_ops.md): Get the ops passing the given filter.

[`filter_ops_from_regex(...)`](../../tf/contrib/graph_editor/filter_ops_from_regex.md): Get all the operations that match the given regex.

[`filter_ts(...)`](../../tf/contrib/graph_editor/filter_ts.md): Get all the tensors which are input or output of an op in ops.

[`filter_ts_from_regex(...)`](../../tf/contrib/graph_editor/filter_ts_from_regex.md): Get all the tensors linked to ops that match the given regex.

[`get_backward_walk_ops(...)`](../../tf/contrib/graph_editor/get_backward_walk_ops.md): Do a backward graph walk and return all the visited ops.

[`get_consuming_ops(...)`](../../tf/contrib/graph_editor/get_consuming_ops.md): Return all the consuming ops of the tensors in ts.

[`get_forward_walk_ops(...)`](../../tf/contrib/graph_editor/get_forward_walk_ops.md): Do a forward graph walk and return all the visited ops.

[`get_generating_ops(...)`](../../tf/contrib/graph_editor/get_generating_ops.md): Return all the generating ops of the tensors in `ts`.

[`get_name_scope_ops(...)`](../../tf/contrib/graph_editor/get_name_scope_ops.md): Get all the operations under the given scope path.

[`get_ops_ios(...)`](../../tf/contrib/graph_editor/get_ops_ios.md): Return all the <a href="../../tf/Operation.md"><code>tf.Operation</code></a> which are connected to an op in ops.

[`get_tensors(...)`](../../tf/contrib/graph_editor/get_tensors.md): get all the tensors which are input or output of an op in the graph.

[`get_walks_intersection_ops(...)`](../../tf/contrib/graph_editor/get_walks_intersection_ops.md): Return the intersection of a forward and a backward walk.

[`get_walks_union_ops(...)`](../../tf/contrib/graph_editor/get_walks_union_ops.md): Return the union of a forward and a backward walk.

[`get_within_boundary_ops(...)`](../../tf/contrib/graph_editor/get_within_boundary_ops.md): Return all the <a href="../../tf/Operation.md"><code>tf.Operation</code></a> within the given boundary.

[`graph_replace(...)`](../../tf/contrib/graph_editor/graph_replace.md): Create a new graph which compute the targets from the replaced Tensors.

[`keep_t_if_possible_handler(...)`](../../tf/contrib/graph_editor/keep_t_if_possible_handler.md): Transform a tensor into itself (identity) if possible.

[`make_list_of_op(...)`](../../tf/contrib/graph_editor/make_list_of_op.md): Convert ops to a list of <a href="../../tf/Operation.md"><code>tf.Operation</code></a>.

[`make_list_of_t(...)`](../../tf/contrib/graph_editor/make_list_of_t.md): Convert ts to a list of <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>.

[`make_placeholder_from_dtype_and_shape(...)`](../../tf/contrib/graph_editor/make_placeholder_from_dtype_and_shape.md): Create a tf.placeholder for the Graph Editor.

[`make_placeholder_from_tensor(...)`](../../tf/contrib/graph_editor/make_placeholder_from_tensor.md): Create a <a href="../../tf/placeholder.md"><code>tf.placeholder</code></a> for the Graph Editor.

[`make_regex(...)`](../../tf/contrib/graph_editor/make_regex.md): Return a compiled regular expression.

[`make_view(...)`](../../tf/contrib/graph_editor/make_view.md): Create a SubGraphView from selected operations and passthrough tensors.

[`make_view_from_scope(...)`](../../tf/contrib/graph_editor/make_view_from_scope.md): Make a subgraph from a name scope.

[`ph(...)`](../../tf/contrib/graph_editor/make_placeholder_from_dtype_and_shape.md): Create a tf.placeholder for the Graph Editor.

[`placeholder_name(...)`](../../tf/contrib/graph_editor/placeholder_name.md): Create placeholder name for the graph editor.

[`remove_control_inputs(...)`](../../tf/contrib/graph_editor/remove_control_inputs.md): Remove the control inputs cops from co.

[`replace_t_with_placeholder_handler(...)`](../../tf/contrib/graph_editor/replace_t_with_placeholder_handler.md): Transform a tensor into a placeholder tensor.

[`reroute_inputs(...)`](../../tf/contrib/graph_editor/reroute_inputs.md): Re-route all the inputs of two subgraphs.

[`reroute_ios(...)`](../../tf/contrib/graph_editor/reroute_ios.md): Re-route the inputs and outputs of sgv0 to sgv1 (see _reroute_sgv).

[`reroute_outputs(...)`](../../tf/contrib/graph_editor/reroute_outputs.md): Re-route all the outputs of two operations.

[`reroute_ts(...)`](../../tf/contrib/graph_editor/reroute_ts.md): For each tensor's pair, replace the end of t1 by the end of t0.

[`select_ops(...)`](../../tf/contrib/graph_editor/select_ops.md): Helper to select operations.

[`select_ops_and_ts(...)`](../../tf/contrib/graph_editor/select_ops_and_ts.md): Helper to select operations and tensors.

[`select_ts(...)`](../../tf/contrib/graph_editor/select_ts.md): Helper to select tensors.

[`sgv(...)`](../../tf/contrib/graph_editor/make_view.md): Create a SubGraphView from selected operations and passthrough tensors.

[`sgv_scope(...)`](../../tf/contrib/graph_editor/make_view_from_scope.md): Make a subgraph from a name scope.

[`swap_inputs(...)`](../../tf/contrib/graph_editor/swap_inputs.md): Swap all the inputs of sgv0 and sgv1 (see reroute_inputs).

[`swap_ios(...)`](../../tf/contrib/graph_editor/swap_ios.md): Swap the inputs and outputs of sgv1 to sgv0 (see _reroute_sgv).

[`swap_outputs(...)`](../../tf/contrib/graph_editor/swap_outputs.md): Swap all the outputs of sgv0 and sgv1 (see reroute_outputs).

[`swap_ts(...)`](../../tf/contrib/graph_editor/swap_ts.md): For each tensor's pair, swap the end of (t0,t1).

[`transform_op_if_inside_handler(...)`](../../tf/contrib/graph_editor/transform_op_if_inside_handler.md): Transform an optional op only if it is inside the subgraph.

