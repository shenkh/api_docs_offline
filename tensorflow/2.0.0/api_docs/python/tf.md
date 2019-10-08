<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__all__"/>
<meta itemprop="property" content="__compiler_version__"/>
<meta itemprop="property" content="__cxx11_abi_flag__"/>
<meta itemprop="property" content="__git_version__"/>
<meta itemprop="property" content="__monolithic_build__"/>
<meta itemprop="property" content="__version__"/>
<meta itemprop="property" content="bfloat16"/>
<meta itemprop="property" content="bool"/>
<meta itemprop="property" content="complex128"/>
<meta itemprop="property" content="complex64"/>
<meta itemprop="property" content="double"/>
<meta itemprop="property" content="float16"/>
<meta itemprop="property" content="float32"/>
<meta itemprop="property" content="float64"/>
<meta itemprop="property" content="half"/>
<meta itemprop="property" content="int16"/>
<meta itemprop="property" content="int32"/>
<meta itemprop="property" content="int64"/>
<meta itemprop="property" content="int8"/>
<meta itemprop="property" content="newaxis"/>
<meta itemprop="property" content="qint16"/>
<meta itemprop="property" content="qint32"/>
<meta itemprop="property" content="qint8"/>
<meta itemprop="property" content="quint16"/>
<meta itemprop="property" content="quint8"/>
<meta itemprop="property" content="resource"/>
<meta itemprop="property" content="string"/>
<meta itemprop="property" content="uint16"/>
<meta itemprop="property" content="uint32"/>
<meta itemprop="property" content="uint64"/>
<meta itemprop="property" content="uint8"/>
<meta itemprop="property" content="variant"/>
</div>

# Module: tf



Defined in [`tensorflow/__init__.py`](/code/stable/tensorflow/__init__.py).

Top-level module of TensorFlow. By convention, we refer to this module as 
<a href="./tf.md"><code>tf</code></a> instead of `tensorflow`, following the common practice of importing 
TensorFlow via the command `import tensorflow as tf`.

The primary function of this module is to import all of the public TensorFlow 
interfaces into a single place. The interfaces themselves are located in 
sub-modules, as described below.

Note that the file `__init__.py` in the TensorFlow source code tree is actually 
only a placeholder to enable test cases to run. The TensorFlow build replaces 
this file with a file generated from [`api_template.__init__.py`](https://www.github.com/tensorflow/tensorflow/blob/master/tensorflow/api_template.__init__.py)

## Modules

[`audio`](./tf/audio.md) module: Public API for tf.audio namespace.

[`autograph`](./tf/autograph.md) module: Conversion of plain Python into TensorFlow graph code.

[`bitwise`](./tf/bitwise.md) module: Operations for manipulating the binary representations of integers.

[`compat`](./tf/compat.md) module: Functions for Python 2 vs. 3 compatibility.

[`config`](./tf/config.md) module: Public API for tf.config namespace.

[`data`](./tf/data.md) module: <a href="./tf/data/Dataset.md"><code>tf.data.Dataset</code></a> API for input pipelines.

[`debugging`](./tf/debugging.md) module: Public API for tf.debugging namespace.

[`distribute`](./tf/distribute.md) module: Library for running a computation across multiple devices.

[`dtypes`](./tf/dtypes.md) module: Public API for tf.dtypes namespace.

[`errors`](./tf/errors.md) module: Exception types for TensorFlow errors.

[`estimator`](./tf/estimator.md) module: Estimator: High level tools for working with models.

[`experimental`](./tf/experimental.md) module: Public API for tf.experimental namespace.

[`feature_column`](./tf/feature_column.md) module: Public API for tf.feature_column namespace.

[`graph_util`](./tf/graph_util.md) module: Helpers to manipulate a tensor graph in python.

[`image`](./tf/image.md) module: Image processing and decoding ops.

[`initializers`](./tf/initializers.md) module: Keras initializer serialization / deserialization.

[`io`](./tf/io.md) module: Public API for tf.io namespace.

[`keras`](./tf/keras.md) module: Implementation of the Keras API meant to be a high-level API for TensorFlow.

[`linalg`](./tf/linalg.md) module: Operations for linear algebra.

[`lite`](./tf/lite.md) module: Public API for tf.lite namespace.

[`lookup`](./tf/lookup.md) module: Public API for tf.lookup namespace.

[`losses`](./tf/losses.md) module: Built-in loss functions.

[`math`](./tf/math.md) module: Math Operations.

[`metrics`](./tf/metrics.md) module: Built-in metrics.

[`nest`](./tf/nest.md) module: Public API for tf.nest namespace.

[`nn`](./tf/nn.md) module: Wrappers for primitive Neural Net (NN) Operations.

[`optimizers`](./tf/optimizers.md) module: Built-in optimizer classes.

[`quantization`](./tf/quantization.md) module: Public API for tf.quantization namespace.

[`queue`](./tf/queue.md) module: Public API for tf.queue namespace.

[`ragged`](./tf/ragged.md) module: Ragged Tensors.

[`random`](./tf/random.md) module: Public API for tf.random namespace.

[`raw_ops`](./tf/raw_ops.md) module: Public API for tf.raw_ops namespace.

[`saved_model`](./tf/saved_model.md) module: Public API for tf.saved_model namespace.

[`sets`](./tf/sets.md) module: Tensorflow set operations.

[`signal`](./tf/signal.md) module: Signal processing operations.

[`sparse`](./tf/sparse.md) module: Sparse Tensor Representation.

[`strings`](./tf/strings.md) module: Operations for working with string Tensors.

[`summary`](./tf/summary.md) module: Operations for writing summary data, for use in analysis and visualization.

[`sysconfig`](./tf/sysconfig.md) module: System configuration library.

[`test`](./tf/test.md) module: Testing.

[`tools`](./tf/tools.md) module

[`tpu`](./tf/tpu.md) module: Ops related to Tensor Processing Units.

[`train`](./tf/train.md) module: Support for training models.

[`version`](./tf/version.md) module: Public API for tf.version namespace.

[`xla`](./tf/xla.md) module: Public API for tf.xla namespace.

## Classes

[`class AggregationMethod`](./tf/AggregationMethod.md): A class listing aggregation methods used to combine gradients.

[`class CriticalSection`](./tf/CriticalSection.md): Critical section.

[`class DType`](./tf/dtypes/DType.md): Represents the type of the elements in a `Tensor`.

[`class DeviceSpec`](./tf/DeviceSpec.md): Represents a (possibly partial) specification for a TensorFlow device.

[`class GradientTape`](./tf/GradientTape.md): Record operations for automatic differentiation.

[`class Graph`](./tf/Graph.md): A TensorFlow computation, represented as a dataflow graph.

[`class IndexedSlices`](./tf/IndexedSlices.md): A sparse representation of a set of tensor slices at given indices.

[`class IndexedSlicesSpec`](./tf/IndexedSlicesSpec.md): Type specification for a <a href="./tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a>.

[`class Module`](./tf/Module.md): Base neural network module class.

[`class Operation`](./tf/Operation.md): Represents a graph node that performs computation on tensors.

[`class OptionalSpec`](./tf/OptionalSpec.md): Represents an optional potentially containing a structured value.

[`class RaggedTensor`](./tf/RaggedTensor.md): Represents a ragged tensor.

[`class RaggedTensorSpec`](./tf/RaggedTensorSpec.md): Type specification for a <a href="./tf/RaggedTensor.md"><code>tf.RaggedTensor</code></a>.

[`class RegisterGradient`](./tf/RegisterGradient.md): A decorator for registering the gradient function for an op type.

[`class SparseTensor`](./tf/sparse/SparseTensor.md): Represents a sparse tensor.

[`class SparseTensorSpec`](./tf/SparseTensorSpec.md): Type specification for a <a href="./tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a>.

[`class Tensor`](./tf/Tensor.md): Represents one of the outputs of an `Operation`.

[`class TensorArray`](./tf/TensorArray.md): Class wrapping dynamic-sized, per-time-step, write-once Tensor arrays.

[`class TensorArraySpec`](./tf/TensorArraySpec.md): Type specification for a <a href="./tf/TensorArray.md"><code>tf.TensorArray</code></a>.

[`class TensorShape`](./tf/TensorShape.md): Represents the shape of a `Tensor`.

[`class TensorSpec`](./tf/TensorSpec.md): Describes a tf.Tensor.

[`class TypeSpec`](./tf/TypeSpec.md): Specifies a TensorFlow value type.

[`class UnconnectedGradients`](./tf/UnconnectedGradients.md): Controls how gradient computation behaves when y does not depend on x.

[`class Variable`](./tf/Variable.md): See the [Variables Guide](https://tensorflow.org/guide/variables).

[`class VariableAggregation`](./tf/VariableAggregation.md): Indicates how a distributed variable will be aggregated.

[`class VariableSynchronization`](./tf/VariableSynchronization.md): Indicates when a distributed variable will be synced.

[`class constant_initializer`](./tf/constant_initializer.md): Initializer that generates tensors with constant values.

[`class name_scope`](./tf/name_scope.md): A context manager for use when defining a Python op.

[`class ones_initializer`](./tf/ones_initializer.md): Initializer that generates tensors initialized to 1.

[`class random_normal_initializer`](./tf/random_normal_initializer.md): Initializer that generates tensors with a normal distribution.

[`class random_uniform_initializer`](./tf/random_uniform_initializer.md): Initializer that generates tensors with a uniform distribution.

[`class zeros_initializer`](./tf/zeros_initializer.md): Initializer that generates tensors initialized to 0.

## Functions

[`Assert(...)`](./tf/debugging/Assert.md): Asserts that the given condition is true.

[`abs(...)`](./tf/math/abs.md): Computes the absolute value of a tensor.

[`acos(...)`](./tf/math/acos.md): Computes acos of x element-wise.

[`acosh(...)`](./tf/math/acosh.md): Computes inverse hyperbolic cosine of x element-wise.

[`add(...)`](./tf/math/add.md): Returns x + y element-wise.

[`add_n(...)`](./tf/math/add_n.md): Adds all input tensors element-wise.

[`argmax(...)`](./tf/math/argmax.md): Returns the index with the largest value across axes of a tensor.

[`argmin(...)`](./tf/math/argmin.md): Returns the index with the smallest value across axes of a tensor.

[`argsort(...)`](./tf/argsort.md): Returns the indices of a tensor that give its sorted order along an axis.

[`as_dtype(...)`](./tf/dtypes/as_dtype.md): Converts the given `type_value` to a `DType`.

[`as_string(...)`](./tf/strings/as_string.md): Converts each entry in the given tensor to strings.

[`asin(...)`](./tf/math/asin.md): Computes the trignometric inverse sine of x element-wise.

[`asinh(...)`](./tf/math/asinh.md): Computes inverse hyperbolic sine of x element-wise.

[`assert_equal(...)`](./tf/debugging/assert_equal.md): Assert the condition `x == y` holds element-wise.

[`assert_greater(...)`](./tf/debugging/assert_greater.md): Assert the condition `x > y` holds element-wise.

[`assert_less(...)`](./tf/debugging/assert_less.md): Assert the condition `x < y` holds element-wise.

[`assert_rank(...)`](./tf/debugging/assert_rank.md): Assert that `x` has rank equal to `rank`.

[`atan(...)`](./tf/math/atan.md): Computes the trignometric inverse tangent of x element-wise.

[`atan2(...)`](./tf/math/atan2.md): Computes arctangent of `y/x` element-wise, respecting signs of the arguments.

[`atanh(...)`](./tf/math/atanh.md): Computes inverse hyperbolic tangent of x element-wise.

[`batch_to_space(...)`](./tf/batch_to_space.md): BatchToSpace for N-D tensors of type T.

[`bitcast(...)`](./tf/bitcast.md): Bitcasts a tensor from one type to another without copying data.

[`boolean_mask(...)`](./tf/boolean_mask.md): Apply boolean mask to tensor.

[`broadcast_dynamic_shape(...)`](./tf/broadcast_dynamic_shape.md): Computes the shape of a broadcast given symbolic shapes.

[`broadcast_static_shape(...)`](./tf/broadcast_static_shape.md): Computes the shape of a broadcast given known shapes.

[`broadcast_to(...)`](./tf/broadcast_to.md): Broadcast an array for a compatible shape.

[`case(...)`](./tf/case.md): Create a case operation.

[`cast(...)`](./tf/dtypes/cast.md): Casts a tensor to a new type.

[`clip_by_global_norm(...)`](./tf/clip_by_global_norm.md): Clips values of multiple tensors by the ratio of the sum of their norms.

[`clip_by_norm(...)`](./tf/clip_by_norm.md): Clips tensor values to a maximum L2-norm.

[`clip_by_value(...)`](./tf/clip_by_value.md): Clips tensor values to a specified min and max.

[`complex(...)`](./tf/dtypes/complex.md): Converts two real numbers to a complex number.

[`concat(...)`](./tf/concat.md): Concatenates tensors along one dimension.

[`cond(...)`](./tf/cond.md): Return `true_fn()` if the predicate `pred` is true else `false_fn()`.

[`constant(...)`](./tf/constant.md): Creates a constant tensor.

[`control_dependencies(...)`](./tf/control_dependencies.md): Wrapper for `Graph.control_dependencies()` using the default graph.

[`convert_to_tensor(...)`](./tf/convert_to_tensor.md): Converts the given `value` to a `Tensor`.

[`cos(...)`](./tf/math/cos.md): Computes cos of x element-wise.

[`cosh(...)`](./tf/math/cosh.md): Computes hyperbolic cosine of x element-wise.

[`cumsum(...)`](./tf/math/cumsum.md): Compute the cumulative sum of the tensor `x` along `axis`.

[`custom_gradient(...)`](./tf/custom_gradient.md): Decorator to define a function with a custom gradient.

[`device(...)`](./tf/device.md): Specifies the device for ops created/executed in this context.

[`divide(...)`](./tf/math/divide.md): Computes Python style division of `x` by `y`.

[`dynamic_partition(...)`](./tf/dynamic_partition.md): Partitions `data` into `num_partitions` tensors using indices from `partitions`.

[`dynamic_stitch(...)`](./tf/dynamic_stitch.md): Interleave the values from the `data` tensors into a single tensor.

[`edit_distance(...)`](./tf/edit_distance.md): Computes the Levenshtein distance between sequences.

[`einsum(...)`](./tf/einsum.md): A generalized contraction between tensors of arbitrary dimension.

[`ensure_shape(...)`](./tf/ensure_shape.md): Updates the shape of a tensor and checks at runtime that the shape holds.

[`equal(...)`](./tf/math/equal.md): Returns the truth value of (x == y) element-wise.

[`executing_eagerly(...)`](./tf/executing_eagerly.md): Returns True if the current thread has eager execution enabled.

[`exp(...)`](./tf/math/exp.md): Computes exponential of x element-wise.  \\(y = e^x\\).

[`expand_dims(...)`](./tf/expand_dims.md): Inserts a dimension of 1 into a tensor's shape.

[`extract_volume_patches(...)`](./tf/extract_volume_patches.md): Extract `patches` from `input` and put them in the "depth" output dimension. 3D extension of `extract_image_patches`.

[`eye(...)`](./tf/eye.md): Construct an identity matrix, or a batch of matrices.

[`fill(...)`](./tf/fill.md): Creates a tensor filled with a scalar value.

[`fingerprint(...)`](./tf/fingerprint.md): Generates fingerprint values.

[`floor(...)`](./tf/math/floor.md): Returns element-wise largest integer not greater than x.

[`foldl(...)`](./tf/foldl.md): foldl on the list of tensors unpacked from `elems` on dimension 0.

[`foldr(...)`](./tf/foldr.md): foldr on the list of tensors unpacked from `elems` on dimension 0.

[`function(...)`](./tf/function.md): Creates a callable TensorFlow graph from a Python function.

[`gather(...)`](./tf/gather.md): Gather slices from params axis axis according to indices.

[`gather_nd(...)`](./tf/gather_nd.md): Gather slices from `params` into a Tensor with shape specified by `indices`.

[`get_logger(...)`](./tf/get_logger.md): Return TF logger instance.

[`get_static_value(...)`](./tf/get_static_value.md): Returns the constant value of the given tensor, if efficiently calculable.

[`grad_pass_through(...)`](./tf/grad_pass_through.md): Creates a grad-pass-through op with the forward behavior provided in f.

[`gradients(...)`](./tf/gradients.md): Constructs symbolic derivatives of sum of `ys` w.r.t. x in `xs`.

[`greater(...)`](./tf/math/greater.md): Returns the truth value of (x > y) element-wise.

[`greater_equal(...)`](./tf/math/greater_equal.md): Returns the truth value of (x >= y) element-wise.

[`group(...)`](./tf/group.md): Create an op that groups multiple operations.

[`guarantee_const(...)`](./tf/guarantee_const.md): Gives a guarantee to the TF runtime that the input tensor is a constant.

[`hessians(...)`](./tf/hessians.md): Constructs the Hessian of sum of `ys` with respect to `x` in `xs`.

[`histogram_fixed_width(...)`](./tf/histogram_fixed_width.md): Return histogram of values.

[`histogram_fixed_width_bins(...)`](./tf/histogram_fixed_width_bins.md): Bins the given values for use in a histogram.

[`identity(...)`](./tf/identity.md): Return a tensor with the same shape and contents as input.

[`identity_n(...)`](./tf/identity_n.md): Returns a list of tensors with the same shapes and contents as the input

[`import_graph_def(...)`](./tf/graph_util/import_graph_def.md): Imports the graph from `graph_def` into the current default `Graph`. (deprecated arguments)

[`init_scope(...)`](./tf/init_scope.md): A context manager that lifts ops out of control-flow scopes and function-building graphs.

[`is_tensor(...)`](./tf/is_tensor.md): Checks whether `x` is a tensor or "tensor-like".

[`less(...)`](./tf/math/less.md): Returns the truth value of (x < y) element-wise.

[`less_equal(...)`](./tf/math/less_equal.md): Returns the truth value of (x <= y) element-wise.

[`linspace(...)`](./tf/linspace.md): Generates values in an interval.

[`load_library(...)`](./tf/load_library.md): Loads a TensorFlow plugin.

[`load_op_library(...)`](./tf/load_op_library.md): Loads a TensorFlow plugin, containing custom ops and kernels.

[`logical_and(...)`](./tf/math/logical_and.md): Returns the truth value of x AND y element-wise.

[`logical_not(...)`](./tf/math/logical_not.md): Returns the truth value of NOT x element-wise.

[`logical_or(...)`](./tf/math/logical_or.md): Returns the truth value of x OR y element-wise.

[`make_ndarray(...)`](./tf/make_ndarray.md): Create a numpy ndarray from a tensor.

[`make_tensor_proto(...)`](./tf/make_tensor_proto.md): Create a TensorProto.

[`map_fn(...)`](./tf/map_fn.md): map on the list of tensors unpacked from `elems` on dimension 0.

[`matmul(...)`](./tf/linalg/matmul.md): Multiplies matrix `a` by matrix `b`, producing `a` * `b`.

[`matrix_square_root(...)`](./tf/linalg/sqrtm.md): Computes the matrix square root of one or more square matrices:

[`maximum(...)`](./tf/math/maximum.md): Returns the max of x and y (i.e. x > y ? x : y) element-wise.

[`meshgrid(...)`](./tf/meshgrid.md): Broadcasts parameters for evaluation on an N-D grid.

[`minimum(...)`](./tf/math/minimum.md): Returns the min of x and y (i.e. x < y ? x : y) element-wise.

[`multiply(...)`](./tf/math/multiply.md): Returns x * y element-wise.

[`negative(...)`](./tf/math/negative.md): Computes numerical negative value element-wise.

[`no_gradient(...)`](./tf/no_gradient.md): Specifies that ops of type `op_type` is not differentiable.

[`no_op(...)`](./tf/no_op.md): Does nothing. Only useful as a placeholder for control edges.

[`nondifferentiable_batch_function(...)`](./tf/nondifferentiable_batch_function.md): Batches the computation done by the decorated function.

[`norm(...)`](./tf/norm.md): Computes the norm of vectors, matrices, and tensors.

[`not_equal(...)`](./tf/math/not_equal.md): Returns the truth value of (x != y) element-wise.

[`numpy_function(...)`](./tf/numpy_function.md): Wraps a python function and uses it as a TensorFlow op.

[`one_hot(...)`](./tf/one_hot.md): Returns a one-hot tensor.

[`ones(...)`](./tf/ones.md): Creates a tensor with all elements set to 1.

[`ones_like(...)`](./tf/ones_like.md): Creates a tensor with all elements set to one.

[`pad(...)`](./tf/pad.md): Pads a tensor.

[`parallel_stack(...)`](./tf/parallel_stack.md): Stacks a list of rank-`R` tensors into one rank-`(R+1)` tensor in parallel.

[`pow(...)`](./tf/math/pow.md): Computes the power of one value to another.

[`print(...)`](./tf/print.md): Print the specified inputs.

[`py_function(...)`](./tf/py_function.md): Wraps a python function into a TensorFlow op that executes it eagerly.

[`range(...)`](./tf/range.md): Creates a sequence of numbers.

[`rank(...)`](./tf/rank.md): Returns the rank of a tensor.

[`realdiv(...)`](./tf/realdiv.md): Returns x / y element-wise for real types.

[`recompute_grad(...)`](./tf/recompute_grad.md): An eager-compatible version of recompute_grad.

[`reduce_all(...)`](./tf/reduce_all.md): Computes the "logical and" of elements across dimensions of a tensor.

[`reduce_any(...)`](./tf/math/reduce_any.md): Computes the "logical or" of elements across dimensions of a tensor.

[`reduce_logsumexp(...)`](./tf/math/reduce_logsumexp.md): Computes log(sum(exp(elements across dimensions of a tensor))).

[`reduce_max(...)`](./tf/math/reduce_max.md): Computes the maximum of elements across dimensions of a tensor.

[`reduce_mean(...)`](./tf/math/reduce_mean.md): Computes the mean of elements across dimensions of a tensor.

[`reduce_min(...)`](./tf/math/reduce_min.md): Computes the minimum of elements across dimensions of a tensor.

[`reduce_prod(...)`](./tf/math/reduce_prod.md): Computes the product of elements across dimensions of a tensor.

[`reduce_sum(...)`](./tf/math/reduce_sum.md): Computes the sum of elements across dimensions of a tensor.

[`register_tensor_conversion_function(...)`](./tf/register_tensor_conversion_function.md): Registers a function for converting objects of `base_type` to `Tensor`.

[`required_space_to_batch_paddings(...)`](./tf/required_space_to_batch_paddings.md): Calculate padding required to make block_shape divide input_shape.

[`reshape(...)`](./tf/reshape.md): Reshapes a tensor.

[`reverse(...)`](./tf/reverse.md): Reverses specific dimensions of a tensor.

[`reverse_sequence(...)`](./tf/reverse_sequence.md): Reverses variable length slices.

[`roll(...)`](./tf/roll.md): Rolls the elements of a tensor along an axis.

[`round(...)`](./tf/math/round.md): Rounds the values of a tensor to the nearest integer, element-wise.

[`saturate_cast(...)`](./tf/dtypes/saturate_cast.md): Performs a safe saturating cast of `value` to `dtype`.

[`scalar_mul(...)`](./tf/math/scalar_mul.md): Multiplies a scalar times a `Tensor` or `IndexedSlices` object.

[`scan(...)`](./tf/scan.md): scan on the list of tensors unpacked from `elems` on dimension 0.

[`scatter_nd(...)`](./tf/scatter_nd.md): Scatter `updates` into a new tensor according to `indices`.

[`searchsorted(...)`](./tf/searchsorted.md): Searches input tensor for values on the innermost dimension.

[`sequence_mask(...)`](./tf/sequence_mask.md): Returns a mask tensor representing the first N positions of each cell.

[`shape(...)`](./tf/shape.md): Returns the shape of a tensor.

[`shape_n(...)`](./tf/shape_n.md): Returns shape of tensors.

[`sigmoid(...)`](./tf/math/sigmoid.md): Computes sigmoid of `x` element-wise.

[`sign(...)`](./tf/math/sign.md): Returns an element-wise indication of the sign of a number.

[`sin(...)`](./tf/math/sin.md): Computes sine of x element-wise.

[`sinh(...)`](./tf/math/sinh.md): Computes hyperbolic sine of x element-wise.

[`size(...)`](./tf/size.md)

[`slice(...)`](./tf/slice.md): Extracts a slice from a tensor.

[`sort(...)`](./tf/sort.md): Sorts a tensor.

[`space_to_batch(...)`](./tf/space_to_batch.md): SpaceToBatch for N-D tensors of type T.

[`space_to_batch_nd(...)`](./tf/space_to_batch_nd.md): SpaceToBatch for N-D tensors of type T.

[`split(...)`](./tf/split.md): Splits a tensor into sub tensors.

[`sqrt(...)`](./tf/math/sqrt.md): Computes square root of x element-wise.

[`square(...)`](./tf/math/square.md): Computes square of x element-wise.

[`squeeze(...)`](./tf/squeeze.md): Removes dimensions of size 1 from the shape of a tensor.

[`stack(...)`](./tf/stack.md): Stacks a list of rank-`R` tensors into one rank-`(R+1)` tensor.

[`stop_gradient(...)`](./tf/stop_gradient.md): Stops gradient computation.

[`strided_slice(...)`](./tf/strided_slice.md): Extracts a strided slice of a tensor (generalized python array indexing).

[`subtract(...)`](./tf/math/subtract.md): Returns x - y element-wise.

[`switch_case(...)`](./tf/switch_case.md): Create a switch/case operation, i.e. an integer-indexed conditional.

[`tan(...)`](./tf/math/tan.md): Computes tan of x element-wise.

[`tanh(...)`](./tf/math/tanh.md): Computes hyperbolic tangent of `x` element-wise.

[`tensor_scatter_nd_add(...)`](./tf/tensor_scatter_nd_add.md): Adds sparse `updates` to an existing tensor according to `indices`.

[`tensor_scatter_nd_sub(...)`](./tf/tensor_scatter_nd_sub.md): Subtracts sparse `updates` from an existing tensor according to `indices`.

[`tensor_scatter_nd_update(...)`](./tf/tensor_scatter_nd_update.md): Scatter `updates` into an existing tensor according to `indices`.

[`tensordot(...)`](./tf/tensordot.md): Tensor contraction of a and b along specified axes.

[`tile(...)`](./tf/tile.md): Constructs a tensor by tiling a given tensor.

[`timestamp(...)`](./tf/timestamp.md): Provides the time since epoch in seconds.

[`transpose(...)`](./tf/transpose.md): Transposes `a`.

[`truediv(...)`](./tf/math/truediv.md): Divides x / y elementwise (using Python 3 division operator semantics).

[`truncatediv(...)`](./tf/truncatediv.md): Returns x / y element-wise for integer types.

[`truncatemod(...)`](./tf/truncatemod.md): Returns element-wise remainder of division. This emulates C semantics in that

[`tuple(...)`](./tf/tuple.md): Group tensors together.

[`unique(...)`](./tf/unique.md): Finds unique elements in a 1-D tensor.

[`unique_with_counts(...)`](./tf/unique_with_counts.md): Finds unique elements in a 1-D tensor.

[`unravel_index(...)`](./tf/unravel_index.md): Converts a flat index or array of flat indices into a tuple of

[`unstack(...)`](./tf/unstack.md): Unpacks the given dimension of a rank-`R` tensor into rank-`(R-1)` tensors.

[`variable_creator_scope(...)`](./tf/variable_creator_scope.md): Scope which defines a variable creation function to be used by variable().

[`vectorized_map(...)`](./tf/vectorized_map.md): Parallel map on the list of tensors unpacked from `elems` on dimension 0.

[`where(...)`](./tf/where.md): Return the elements, either from `x` or `y`, depending on the `condition`.

[`while_loop(...)`](./tf/while_loop.md): Repeat `body` while the condition `cond` is true.

[`zeros(...)`](./tf/zeros.md): Creates a tensor with all elements set to zero.

[`zeros_like(...)`](./tf/zeros_like.md): Creates a tensor with all elements set to zero.

## Other Members

<h3 id="__all__"><code>__all__</code></h3>

<h3 id="__compiler_version__"><code>__compiler_version__</code></h3>

<h3 id="__cxx11_abi_flag__"><code>__cxx11_abi_flag__</code></h3>

<h3 id="__git_version__"><code>__git_version__</code></h3>

<h3 id="__monolithic_build__"><code>__monolithic_build__</code></h3>

<h3 id="__version__"><code>__version__</code></h3>

<h3 id="bfloat16"><code>bfloat16</code></h3>

<h3 id="bool"><code>bool</code></h3>

<h3 id="complex128"><code>complex128</code></h3>

<h3 id="complex64"><code>complex64</code></h3>

<h3 id="double"><code>double</code></h3>

<h3 id="float16"><code>float16</code></h3>

<h3 id="float32"><code>float32</code></h3>

<h3 id="float64"><code>float64</code></h3>

<h3 id="half"><code>half</code></h3>

<h3 id="int16"><code>int16</code></h3>

<h3 id="int32"><code>int32</code></h3>

<h3 id="int64"><code>int64</code></h3>

<h3 id="int8"><code>int8</code></h3>

<h3 id="newaxis"><code>newaxis</code></h3>

<h3 id="qint16"><code>qint16</code></h3>

<h3 id="qint32"><code>qint32</code></h3>

<h3 id="qint8"><code>qint8</code></h3>

<h3 id="quint16"><code>quint16</code></h3>

<h3 id="quint8"><code>quint8</code></h3>

<h3 id="resource"><code>resource</code></h3>

<h3 id="string"><code>string</code></h3>

<h3 id="uint16"><code>uint16</code></h3>

<h3 id="uint32"><code>uint32</code></h3>

<h3 id="uint64"><code>uint64</code></h3>

<h3 id="uint8"><code>uint8</code></h3>

<h3 id="variant"><code>variant</code></h3>

