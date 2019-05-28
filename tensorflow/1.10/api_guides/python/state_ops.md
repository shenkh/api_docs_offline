# Variables

Note: Functions taking `Tensor` arguments can also take anything accepted by
<a href="../../api_docs/python/tf/convert_to_tensor.md"><code>tf.convert_to_tensor</code></a>.

[TOC]

<h2 id="Variables">Variables</h2>

*   <a href="../../api_docs/python/tf/Variable.md"><code>tf.Variable</code></a>

<h2 id="Variable_helper_functions">Variable helper functions</h2>

TensorFlow provides a set of functions to help manage the set of variables
collected in the graph.

*   <a href="../../api_docs/python/tf/global_variables.md"><code>tf.global_variables</code></a>
*   <a href="../../api_docs/python/tf/local_variables.md"><code>tf.local_variables</code></a>
*   <a href="../../api_docs/python/tf/model_variables.md"><code>tf.model_variables</code></a>
*   <a href="../../api_docs/python/tf/trainable_variables.md"><code>tf.trainable_variables</code></a>
*   <a href="../../api_docs/python/tf/moving_average_variables.md"><code>tf.moving_average_variables</code></a>
*   <a href="../../api_docs/python/tf/global_variables_initializer.md"><code>tf.global_variables_initializer</code></a>
*   <a href="../../api_docs/python/tf/local_variables_initializer.md"><code>tf.local_variables_initializer</code></a>
*   <a href="../../api_docs/python/tf/variables_initializer.md"><code>tf.variables_initializer</code></a>
*   <a href="../../api_docs/python/tf/is_variable_initialized.md"><code>tf.is_variable_initialized</code></a>
*   <a href="../../api_docs/python/tf/report_uninitialized_variables.md"><code>tf.report_uninitialized_variables</code></a>
*   <a href="../../api_docs/python/tf/assert_variables_initialized.md"><code>tf.assert_variables_initialized</code></a>
*   <a href="../../api_docs/python/tf/assign.md"><code>tf.assign</code></a>
*   <a href="../../api_docs/python/tf/assign_add.md"><code>tf.assign_add</code></a>
*   <a href="../../api_docs/python/tf/assign_sub.md"><code>tf.assign_sub</code></a>

<h2 id="Saving_and_Restoring_Variables">Saving and Restoring Variables</h2>

*   <a href="../../api_docs/python/tf/train/Saver.md"><code>tf.train.Saver</code></a>
*   <a href="../../api_docs/python/tf/train/latest_checkpoint.md"><code>tf.train.latest_checkpoint</code></a>
*   <a href="../../api_docs/python/tf/train/get_checkpoint_state.md"><code>tf.train.get_checkpoint_state</code></a>
*   <a href="../../api_docs/python/tf/train/update_checkpoint_state.md"><code>tf.train.update_checkpoint_state</code></a>

<h2 id="Sharing_Variables">Sharing Variables</h2>

TensorFlow provides several classes and operations that you can use to
create variables contingent on certain conditions.

*   <a href="../../api_docs/python/tf/get_variable.md"><code>tf.get_variable</code></a>
*   <a href="../../api_docs/python/tf/get_local_variable.md"><code>tf.get_local_variable</code></a>
*   <a href="../../api_docs/python/tf/VariableScope.md"><code>tf.VariableScope</code></a>
*   <a href="../../api_docs/python/tf/variable_scope.md"><code>tf.variable_scope</code></a>
*   <a href="../../api_docs/python/tf/variable_op_scope.md"><code>tf.variable_op_scope</code></a>
*   <a href="../../api_docs/python/tf/get_variable_scope.md"><code>tf.get_variable_scope</code></a>
*   <a href="../../api_docs/python/tf/make_template.md"><code>tf.make_template</code></a>
*   <a href="../../api_docs/python/tf/no_regularizer.md"><code>tf.no_regularizer</code></a>
*   <a href="../../api_docs/python/tf/constant_initializer.md"><code>tf.constant_initializer</code></a>
*   <a href="../../api_docs/python/tf/random_normal_initializer.md"><code>tf.random_normal_initializer</code></a>
*   <a href="../../api_docs/python/tf/truncated_normal_initializer.md"><code>tf.truncated_normal_initializer</code></a>
*   <a href="../../api_docs/python/tf/random_uniform_initializer.md"><code>tf.random_uniform_initializer</code></a>
*   <a href="../../api_docs/python/tf/uniform_unit_scaling_initializer.md"><code>tf.uniform_unit_scaling_initializer</code></a>
*   <a href="../../api_docs/python/tf/zeros_initializer.md"><code>tf.zeros_initializer</code></a>
*   <a href="../../api_docs/python/tf/ones_initializer.md"><code>tf.ones_initializer</code></a>
*   <a href="../../api_docs/python/tf/orthogonal_initializer.md"><code>tf.orthogonal_initializer</code></a>

<h2 id="Variable_Partitioners_for_Sharding">Variable Partitioners for Sharding</h2>

*   <a href="../../api_docs/python/tf/fixed_size_partitioner.md"><code>tf.fixed_size_partitioner</code></a>
*   <a href="../../api_docs/python/tf/variable_axis_size_partitioner.md"><code>tf.variable_axis_size_partitioner</code></a>
*   <a href="../../api_docs/python/tf/min_max_variable_partitioner.md"><code>tf.min_max_variable_partitioner</code></a>

<h2 id="Sparse_Variable_Updates">Sparse Variable Updates</h2>

The sparse update ops modify a subset of the entries in a dense `Variable`,
either overwriting the entries or adding / subtracting a delta.  These are
useful for training embedding models and similar lookup-based networks, since
only a small subset of embedding vectors change in any given step.

Since a sparse update of a large tensor may be generated automatically during
gradient computation (as in the gradient of
<a href="../../api_docs/python/tf/gather.md"><code>tf.gather</code></a>),
an <a href="../../api_docs/python/tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a> class is provided that encapsulates a set
of sparse indices and values.  `IndexedSlices` objects are detected and handled
automatically by the optimizers in most cases.

*   <a href="../../api_docs/python/tf/scatter_update.md"><code>tf.scatter_update</code></a>
*   <a href="../../api_docs/python/tf/scatter_add.md"><code>tf.scatter_add</code></a>
*   <a href="../../api_docs/python/tf/scatter_sub.md"><code>tf.scatter_sub</code></a>
*   <a href="../../api_docs/python/tf/scatter_mul.md"><code>tf.scatter_mul</code></a>
*   <a href="../../api_docs/python/tf/scatter_div.md"><code>tf.scatter_div</code></a>
*   <a href="../../api_docs/python/tf/scatter_min.md"><code>tf.scatter_min</code></a>
*   <a href="../../api_docs/python/tf/scatter_max.md"><code>tf.scatter_max</code></a>
*   <a href="../../api_docs/python/tf/scatter_nd_update.md"><code>tf.scatter_nd_update</code></a>
*   <a href="../../api_docs/python/tf/scatter_nd_add.md"><code>tf.scatter_nd_add</code></a>
*   <a href="../../api_docs/python/tf/scatter_nd_sub.md"><code>tf.scatter_nd_sub</code></a>
*   <a href="../../api_docs/python/tf/sparse_mask.md"><code>tf.sparse_mask</code></a>
*   <a href="../../api_docs/python/tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a>

### Read-only Lookup Tables

*   <a href="../../api_docs/python/tf/initialize_all_tables.md"><code>tf.initialize_all_tables</code></a>
*   <a href="../../api_docs/python/tf/tables_initializer.md"><code>tf.tables_initializer</code></a>


<h2 id="Exporting_and_Importing_Meta_Graphs">Exporting and Importing Meta Graphs</h2>

*   <a href="../../api_docs/python/tf/train/export_meta_graph.md"><code>tf.train.export_meta_graph</code></a>
*   <a href="../../api_docs/python/tf/train/import_meta_graph.md"><code>tf.train.import_meta_graph</code></a>

# Deprecated functions (removed after 2017-03-02). Please don't use them.

*   <a href="../../api_docs/python/tf/all_variables.md"><code>tf.all_variables</code></a>
*   <a href="../../api_docs/python/tf/initialize_all_variables.md"><code>tf.initialize_all_variables</code></a>
*   <a href="../../api_docs/python/tf/initialize_local_variables.md"><code>tf.initialize_local_variables</code></a>
*   <a href="../../api_docs/python/tf/initialize_variables.md"><code>tf.initialize_variables</code></a>
