<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.contrib.framework



Defined in [`tensorflow/contrib/framework/__init__.py`](/code/stable/tensorflow/contrib/framework/__init__.py).

Framework utilities.

See the
[Contrib Framework](https://tensorflow.org/api_guides/python/contrib.framework)
guide.













## Modules

[`nest`](../../tf/contrib/framework/nest.md) module: ## Functions for working with arbitrarily nested sequences of elements.

## Classes

[`class BoundedTensorSpec`](../../tf/contrib/framework/BoundedTensorSpec.md): A `TensorSpec` that specifies minimum and maximum values.

[`class CriticalSection`](../../tf/contrib/framework/CriticalSection.md): Critical section.

[`class RecordInput`](../../tf/contrib/framework/RecordInput.md): RecordInput asynchronously reads and randomly yields TFRecords.

[`class TensorSpec`](../../tf/contrib/eager/TensorSpec.md): Describes a tf.Tensor.

[`class VariableDeviceChooser`](../../tf/contrib/framework/VariableDeviceChooser.md): Device chooser for variables.

[`class convolutional_delta_orthogonal`](../../tf/contrib/framework/convolutional_delta_orthogonal.md): Initializer that generates a delta orthogonal kernel for ConvNets.

[`class convolutional_orthogonal_1d`](../../tf/contrib/framework/convolutional_orthogonal_1d.md): Initializer that generates a 1D orthogonal kernel for ConvNets.

[`class convolutional_orthogonal_2d`](../../tf/contrib/framework/convolutional_orthogonal_2d.md): Initializer that generates a 2D orthogonal kernel for ConvNets.

[`class convolutional_orthogonal_3d`](../../tf/contrib/framework/convolutional_orthogonal_3d.md): Initializer that generates a 3D orthogonal kernel for ConvNets.

## Functions

[`add_arg_scope(...)`](../../tf/contrib/framework/add_arg_scope.md): Decorates a function with args so it can be used within an arg_scope.

[`add_model_variable(...)`](../../tf/contrib/framework/add_model_variable.md): Adds a variable to the `GraphKeys.MODEL_VARIABLES` collection.

[`arg_scope(...)`](../../tf/contrib/framework/arg_scope.md): Stores the default arguments for the given set of list_ops.

[`arg_scoped_arguments(...)`](../../tf/contrib/framework/arg_scoped_arguments.md): Returns the list kwargs that arg_scope can set for a func.

[`argsort(...)`](../../tf/contrib/framework/argsort.md): Returns the indices of a tensor that give its sorted order along an axis.

[`assert_global_step(...)`](../../tf/contrib/framework/assert_global_step.md): DEPRECATED FUNCTION

[`assert_or_get_global_step(...)`](../../tf/contrib/framework/assert_or_get_global_step.md): Verifies that a global step tensor is valid or gets one if None is given.

[`assert_same_float_dtype(...)`](../../tf/debugging/assert_same_float_dtype.md): Validate and return float type based on `tensors` and `dtype`.

[`assert_scalar(...)`](../../tf/debugging/assert_scalar.md)

[`assert_scalar_int(...)`](../../tf/contrib/framework/assert_scalar_int.md): Assert `tensor` is 0-D, of type <a href="../../tf.md#int32"><code>tf.int32</code></a> or <a href="../../tf.md#int64"><code>tf.int64</code></a>.

[`assign_from_checkpoint(...)`](../../tf/contrib/framework/assign_from_checkpoint.md): Creates an operation to assign specific variables from a checkpoint.

[`assign_from_checkpoint_fn(...)`](../../tf/contrib/framework/assign_from_checkpoint_fn.md): Returns a function that assigns specific variables from a checkpoint.

[`assign_from_values(...)`](../../tf/contrib/framework/assign_from_values.md): Creates an assignment operation from a given mapping.

[`assign_from_values_fn(...)`](../../tf/contrib/framework/assign_from_values_fn.md): Returns a function that assigns specific variables from the given values.

[`convert_to_tensor_or_sparse_tensor(...)`](../../tf/convert_to_tensor_or_sparse_tensor.md): Converts value to a `SparseTensor` or `Tensor`.

[`create_global_step(...)`](../../tf/contrib/framework/create_global_step.md): Create global step tensor in graph. (deprecated)

[`current_arg_scope(...)`](../../tf/contrib/framework/current_arg_scope.md)

[`deprecated(...)`](../../tf/contrib/framework/deprecated.md): Decorator for marking functions or methods deprecated.

[`deprecated_arg_values(...)`](../../tf/contrib/framework/deprecated_arg_values.md): Decorator for marking specific function argument values as deprecated.

[`deprecated_args(...)`](../../tf/contrib/framework/deprecated_args.md): Decorator for marking specific function arguments as deprecated.

[`filter_variables(...)`](../../tf/contrib/framework/filter_variables.md): Filter a list of variables using regular expressions.

[`fuse_op(...)`](../../tf/contrib/framework/fuse_op.md): Fuse subgraph between input_nodes and output_nodes into a single custom op.

[`get_global_step(...)`](../../tf/contrib/framework/get_global_step.md): DEPRECATED FUNCTION

[`get_graph_from_inputs(...)`](../../tf/contrib/framework/get_graph_from_inputs.md): Returns the appropriate graph to use for the given inputs.

[`get_local_variables(...)`](../../tf/contrib/framework/get_local_variables.md): Gets the list of local variables, filtered by scope and/or suffix.

[`get_model_variables(...)`](../../tf/contrib/framework/get_model_variables.md): Gets the list of model variables, filtered by scope and/or suffix.

[`get_name_scope(...)`](../../tf/contrib/framework/get_name_scope.md): Returns the current name scope of the default graph.

[`get_or_create_global_step(...)`](../../tf/contrib/framework/get_or_create_global_step.md): Returns and create (if necessary) the global step tensor. (deprecated)

[`get_placeholders(...)`](../../tf/contrib/framework/get_placeholders.md): Get placeholders of a graph.

[`get_trainable_variables(...)`](../../tf/contrib/framework/get_trainable_variables.md): Gets the list of trainable variables, filtered by scope and/or suffix.

[`get_unique_variable(...)`](../../tf/contrib/framework/get_unique_variable.md): Gets the variable uniquely identified by that var_op_name.

[`get_variable_full_name(...)`](../../tf/contrib/framework/get_variable_full_name.md): Returns the full name of a variable.

[`get_variables(...)`](../../tf/contrib/framework/get_variables.md): Gets the list of variables, filtered by scope and/or suffix.

[`get_variables_by_name(...)`](../../tf/contrib/framework/get_variables_by_name.md): Gets the list of variables that were given that name.

[`get_variables_by_suffix(...)`](../../tf/contrib/framework/get_variables_by_suffix.md): Gets the list of variables that end with the given suffix.

[`get_variables_to_restore(...)`](../../tf/contrib/framework/get_variables_to_restore.md): Gets the list of the variables to restore.

[`global_variable(...)`](../../tf/contrib/framework/global_variable.md): Create a variable with a value and add it to `GraphKeys.GLOBAL_VARIABLES`.

[`has_arg_scope(...)`](../../tf/contrib/framework/has_arg_scope.md): Checks whether a func has been decorated with @add_arg_scope or not.

[`init_from_checkpoint(...)`](../../tf/contrib/framework/init_from_checkpoint.md): Using assignment map initializes current variables with loaded tensors.

[`is_tensor(...)`](../../tf/contrib/framework/is_tensor.md): Check whether `x` is of tensor type.

[`list_variables(...)`](../../tf/contrib/framework/list_variables.md): Returns list of all variables in the latest checkpoint.

[`load_and_remap_matrix_initializer(...)`](../../tf/contrib/framework/load_and_remap_matrix_initializer.md): Returns a var initializer for loading and remapping a 2-D (matrix) tensor.

[`load_checkpoint(...)`](../../tf/contrib/framework/load_checkpoint.md): Returns CheckpointReader for latest checkpoint.

[`load_embedding_initializer(...)`](../../tf/contrib/framework/load_embedding_initializer.md): Returns a variable initializer for loading pre-trained embeddings.

[`load_linear_multiclass_bias_initializer(...)`](../../tf/contrib/framework/load_linear_multiclass_bias_initializer.md): Loads pre-trained multi-class biases for linear models from checkpoint.

[`load_variable(...)`](../../tf/contrib/framework/load_variable.md): Returns a Tensor with the contents of the given variable in the checkpoint.

[`load_variable_slot_initializer(...)`](../../tf/contrib/framework/load_variable_slot_initializer.md): Loads pre-trained multi-class slots for linear models from checkpoint.

[`local_variable(...)`](../../tf/contrib/framework/local_variable.md): Create a variable with a value and add it to `GraphKeys.LOCAL_VARIABLES`.

[`model_variable(...)`](../../tf/contrib/framework/model_variable.md): Gets an existing model variable with these parameters or creates a new one.

[`prepend_name_scope(...)`](../../tf/contrib/framework/prepend_name_scope.md): Prepends name scope to a name.

[`py_func(...)`](../../tf/contrib/framework/py_func.md): Wraps a python function and uses it as a TensorFlow op.

[`reduce_sum_n(...)`](../../tf/contrib/framework/reduce_sum_n.md): Reduce tensors to a scalar sum.

[`remove_squeezable_dimensions(...)`](../../tf/contrib/framework/remove_squeezable_dimensions.md): Squeeze last dim if ranks of `predictions` and `labels` differ by 1. (deprecated)

[`smart_case(...)`](../../tf/contrib/framework/smart_case.md): Like tf.case, except attempts to statically evaluate predicates.

[`smart_cond(...)`](../../tf/contrib/framework/smart_cond.md): Return either `true_fn()` if predicate `pred` is true else `false_fn()`.

[`smart_constant_value(...)`](../../tf/contrib/framework/smart_constant_value.md): Return the bool value for `pred`, or None if `pred` had a dynamic value.

[`sort(...)`](../../tf/contrib/framework/sort.md): Sorts a tensor.

[`strip_name_scope(...)`](../../tf/contrib/framework/strip_name_scope.md): Removes name scope from a name.

[`variable(...)`](../../tf/contrib/framework/variable.md): Gets an existing variable with these parameters or creates a new one.

[`with_same_shape(...)`](../../tf/contrib/framework/with_same_shape.md): Assert tensors are the same shape, from the same graph.

[`with_shape(...)`](../../tf/contrib/framework/with_shape.md): Asserts tensor has expected shape.

[`zero_initializer(...)`](../../tf/contrib/framework/zero_initializer.md): Initialize 'ref' with all zeros, ref tensor should be uninitialized.

