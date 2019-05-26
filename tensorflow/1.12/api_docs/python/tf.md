<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="AUTO_REUSE"/>
<meta itemprop="property" content="COMPILER_VERSION"/>
<meta itemprop="property" content="CXX11_ABI_FLAG"/>
<meta itemprop="property" content="GIT_VERSION"/>
<meta itemprop="property" content="GRAPH_DEF_VERSION"/>
<meta itemprop="property" content="GRAPH_DEF_VERSION_MIN_CONSUMER"/>
<meta itemprop="property" content="GRAPH_DEF_VERSION_MIN_PRODUCER"/>
<meta itemprop="property" content="MONOLITHIC_BUILD"/>
<meta itemprop="property" content="QUANTIZED_DTYPES"/>
<meta itemprop="property" content="VERSION"/>
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

Bring in all of the public TensorFlow interface into this module.

## Modules

[`app`](./tf/app.md) module: Generic entry point script.

[`bitwise`](./tf/bitwise.md) module: Operations for manipulating the binary representations of integers.

[`compat`](./tf/compat.md) module: Functions for Python 2 vs. 3 compatibility.

[`contrib`](./tf/contrib.md) module: contrib module containing volatile or experimental code.

[`data`](./tf/data.md) module: <a href="./tf/data/Dataset.md"><code>tf.data.Dataset</code></a> API for input pipelines.

[`debugging`](./tf/debugging.md) module: Public API for tf.debugging namespace.

[`distributions`](./tf/distributions.md) module: Core module for TensorFlow distribution objects and helpers.

[`dtypes`](./tf/dtypes.md) module: Public API for tf.dtypes namespace.

[`errors`](./tf/errors.md) module: Exception types for TensorFlow errors.

[`estimator`](./tf/estimator.md) module: Estimator: High level tools for working with models.

[`feature_column`](./tf/feature_column.md) module: Public API for tf.feature_column namespace.

[`flags`](./tf/app/flags.md) module: Import router for absl.flags. See https://github.com/abseil/abseil-py.

[`gfile`](./tf/gfile.md) module: Import router for file_io.

[`graph_util`](./tf/graph_util.md) module: Helpers to manipulate a tensor graph in python.

[`image`](./tf/image.md) module: Image processing and decoding ops.

[`initializers`](./tf/initializers.md) module: Public API for tf.initializers namespace.

[`io`](./tf/io.md) module: Public API for tf.io namespace.

[`keras`](./tf/keras.md) module: Implementation of the Keras API meant to be a high-level API for TensorFlow.

[`layers`](./tf/layers.md) module: Public API for tf.layers namespace.

[`linalg`](./tf/linalg.md) module: Operations for linear algebra.

[`logging`](./tf/logging.md) module: Logging and Summary Operations.

[`losses`](./tf/losses.md) module: Loss operations for use in neural networks.

[`manip`](./tf/manip.md) module: Operators for manipulating tensors.

[`math`](./tf/math.md) module: Basic arithmetic operators.

[`metrics`](./tf/metrics.md) module: Evaluation-related metrics.

[`nn`](./tf/nn.md) module: Wrappers for primitive Neural Net (NN) Operations.

[`profiler`](./tf/profiler.md) module: Public API for tf.profiler namespace.

[`python_io`](./tf/python_io.md) module: Python functions for directly manipulating TFRecord-formatted files.

[`pywrap_tensorflow`](./tf/pywrap_tensorflow.md) module: A wrapper for TensorFlow SWIG-generated bindings.

[`quantization`](./tf/quantization.md) module: Public API for tf.quantization namespace.

[`random`](./tf/random.md) module: Public API for tf.random namespace.

[`resource_loader`](./tf/resource_loader.md) module: Resource management library.

[`saved_model`](./tf/saved_model.md) module: Public API for tf.saved_model namespace.

[`sets`](./tf/sets.md) module: Tensorflow set operations.

[`sparse`](./tf/sparse.md) module: Sparse Tensor Representation.

[`spectral`](./tf/spectral.md) module: Spectral operators (e.g. DCT, FFT, RFFT).

[`strings`](./tf/strings.md) module: Operations for working with string Tensors.

[`summary`](./tf/summary.md) module: Public API for tf.summary namespace.

[`sysconfig`](./tf/sysconfig.md) module: System configuration library.

[`test`](./tf/test.md) module: Testing.

[`tools`](./tf/tools.md) module

[`train`](./tf/train.md) module: Support for training models.

[`user_ops`](./tf/user_ops.md) module: Public API for tf.user_ops namespace.

## Classes

[`class AggregationMethod`](./tf/AggregationMethod.md): A class listing aggregation methods used to combine gradients.

[`class AttrValue`](./tf/AttrValue.md): A ProtocolMessage

[`class ConditionalAccumulator`](./tf/ConditionalAccumulator.md): A conditional accumulator for aggregating gradients.

[`class ConditionalAccumulatorBase`](./tf/ConditionalAccumulatorBase.md): A conditional accumulator for aggregating gradients.

[`class ConfigProto`](./tf/ConfigProto.md): A ProtocolMessage

[`class DType`](./tf/dtypes/DType.md): Represents the type of the elements in a `Tensor`.

[`class DeviceSpec`](./tf/DeviceSpec.md): Represents a (possibly partial) specification for a TensorFlow device.

[`class Dimension`](./tf/Dimension.md): Represents the value of one dimension in a TensorShape.

[`class Event`](./tf/Event.md): A ProtocolMessage

[`class FIFOQueue`](./tf/FIFOQueue.md): A queue implementation that dequeues elements in first-in first-out order.

[`class FixedLenFeature`](./tf/io/FixedLenFeature.md): Configuration for parsing a fixed-length input feature.

[`class FixedLenSequenceFeature`](./tf/io/FixedLenSequenceFeature.md): Configuration for parsing a variable-length input feature into a `Tensor`.

[`class FixedLengthRecordReader`](./tf/FixedLengthRecordReader.md): A Reader that outputs fixed-length records from a file.

[`class GPUOptions`](./tf/GPUOptions.md): A ProtocolMessage

[`class GradientTape`](./tf/GradientTape.md): Record operations for automatic differentiation.

[`class Graph`](./tf/Graph.md): A TensorFlow computation, represented as a dataflow graph.

[`class GraphDef`](./tf/GraphDef.md): A ProtocolMessage

[`class GraphKeys`](./tf/GraphKeys.md): Standard names to use for graph collections.

[`class GraphOptions`](./tf/GraphOptions.md): A ProtocolMessage

[`class HistogramProto`](./tf/HistogramProto.md): A ProtocolMessage

[`class IdentityReader`](./tf/IdentityReader.md): A Reader that outputs the queued work as both the key and value.

[`class IndexedSlices`](./tf/IndexedSlices.md): A sparse representation of a set of tensor slices at given indices.

[`class InteractiveSession`](./tf/InteractiveSession.md): A TensorFlow `Session` for use in interactive contexts, such as a shell.

[`class LMDBReader`](./tf/LMDBReader.md): A Reader that outputs the records from a LMDB file.

[`class LogMessage`](./tf/LogMessage.md): A ProtocolMessage

[`class MetaGraphDef`](./tf/MetaGraphDef.md): A ProtocolMessage

[`class NameAttrList`](./tf/NameAttrList.md): A ProtocolMessage

[`class NodeDef`](./tf/NodeDef.md): A ProtocolMessage

[`class OpError`](./tf/errors/OpError.md): A generic error that is raised when TensorFlow execution fails.

[`class Operation`](./tf/Operation.md): Represents a graph node that performs computation on tensors.

[`class OptimizerOptions`](./tf/OptimizerOptions.md): A ProtocolMessage

[`class PaddingFIFOQueue`](./tf/io/PaddingFIFOQueue.md): A FIFOQueue that supports batching variable-sized tensors by padding.

[`class PriorityQueue`](./tf/io/PriorityQueue.md): A queue implementation that dequeues elements in prioritized order.

[`class QueueBase`](./tf/io/QueueBase.md): Base class for queue implementations.

[`class RandomShuffleQueue`](./tf/io/RandomShuffleQueue.md): A queue implementation that dequeues elements in a random order.

[`class ReaderBase`](./tf/ReaderBase.md): Base class for different Reader types, that produce a record every step.

[`class RegisterGradient`](./tf/RegisterGradient.md): A decorator for registering the gradient function for an op type.

[`class RunMetadata`](./tf/RunMetadata.md): A ProtocolMessage

[`class RunOptions`](./tf/RunOptions.md): A ProtocolMessage

[`class Session`](./tf/Session.md): A class for running TensorFlow operations.

[`class SessionLog`](./tf/SessionLog.md): A ProtocolMessage

[`class SparseConditionalAccumulator`](./tf/sparse/SparseConditionalAccumulator.md): A conditional accumulator for aggregating sparse gradients.

[`class SparseFeature`](./tf/io/SparseFeature.md): Configuration for parsing a sparse input feature from an `Example`.

[`class SparseTensor`](./tf/sparse/SparseTensor.md): Represents a sparse tensor.

[`class SparseTensorValue`](./tf/SparseTensorValue.md): SparseTensorValue(indices, values, dense_shape)

[`class Summary`](./tf/Summary.md): A ProtocolMessage

[`class SummaryMetadata`](./tf/SummaryMetadata.md): A ProtocolMessage

[`class TFRecordReader`](./tf/TFRecordReader.md): A Reader that outputs the records from a TFRecords file.

[`class Tensor`](./tf/Tensor.md): Represents one of the outputs of an `Operation`.

[`class TensorArray`](./tf/TensorArray.md): Class wrapping dynamic-sized, per-time-step, write-once Tensor arrays.

[`class TensorInfo`](./tf/TensorInfo.md): A ProtocolMessage

[`class TensorShape`](./tf/TensorShape.md): Represents the shape of a `Tensor`.

[`class TextLineReader`](./tf/TextLineReader.md): A Reader that outputs the lines of a file delimited by newlines.

[`class VarLenFeature`](./tf/io/VarLenFeature.md): Configuration for parsing a variable-length input feature.

[`class Variable`](./tf/Variable.md): See the [Variables Guide](https://tensorflow.org/guide/variables).

[`class VariableAggregation`](./tf/VariableAggregation.md): Indicates how a distributed variable will be aggregated.

[`class VariableScope`](./tf/VariableScope.md): Variable scope object to carry defaults to provide to `get_variable`.

[`class VariableSynchronization`](./tf/VariableSynchronization.md): Indicates when a distributed variable will be synced.

[`class WholeFileReader`](./tf/WholeFileReader.md): A Reader that outputs the entire contents of a file as a value.

[`class constant_initializer`](./tf/keras/initializers/Constant.md): Initializer that generates tensors with constant values.

[`class glorot_normal_initializer`](./tf/keras/initializers/glorot_normal.md): The Glorot normal initializer, also called Xavier normal initializer.

[`class glorot_uniform_initializer`](./tf/glorot_uniform_initializer.md): The Glorot uniform initializer, also called Xavier uniform initializer.

[`class name_scope`](./tf/name_scope.md): A context manager for use when defining a Python op.

[`class ones_initializer`](./tf/keras/initializers/Ones.md): Initializer that generates tensors initialized to 1.

[`class orthogonal_initializer`](./tf/keras/initializers/Orthogonal.md): Initializer that generates an orthogonal matrix.

[`class random_normal_initializer`](./tf/initializers/random_normal.md): Initializer that generates tensors with a normal distribution.

[`class random_uniform_initializer`](./tf/initializers/random_uniform.md): Initializer that generates tensors with a uniform distribution.

[`class truncated_normal_initializer`](./tf/initializers/truncated_normal.md): Initializer that generates a truncated normal distribution.

[`class uniform_unit_scaling_initializer`](./tf/initializers/uniform_unit_scaling.md): Initializer that generates tensors without scaling variance.

[`class variable_scope`](./tf/variable_scope.md): A context manager for defining ops that creates variables (layers).

[`class variance_scaling_initializer`](./tf/keras/initializers/VarianceScaling.md): Initializer capable of adapting its scale to the shape of weights tensors.

[`class zeros_initializer`](./tf/keras/initializers/Zeros.md): Initializer that generates tensors initialized to 0.

## Functions

[`Assert(...)`](./tf/debugging/Assert.md): Asserts that the given condition is true.

[`NoGradient(...)`](./tf/NoGradient.md): Specifies that ops of type `op_type` is not differentiable.

[`NotDifferentiable(...)`](./tf/NoGradient.md): Specifies that ops of type `op_type` is not differentiable.

[`Print(...)`](./tf/Print.md): Prints a list of tensors. (deprecated)

[`abs(...)`](./tf/math/abs.md): Computes the absolute value of a tensor.

[`accumulate_n(...)`](./tf/math/accumulate_n.md): Returns the element-wise sum of a list of tensors.

[`acos(...)`](./tf/math/acos.md): Computes acos of x element-wise.

[`acosh(...)`](./tf/math/acosh.md): Computes inverse hyperbolic cosine of x element-wise.

[`add(...)`](./tf/math/add.md): Returns x + y element-wise.

[`add_check_numerics_ops(...)`](./tf/add_check_numerics_ops.md): Connect a `check_numerics` to every floating point tensor.

[`add_n(...)`](./tf/math/add_n.md): Adds all input tensors element-wise.

[`add_to_collection(...)`](./tf/add_to_collection.md): Wrapper for `Graph.add_to_collection()` using the default graph.

[`add_to_collections(...)`](./tf/add_to_collections.md): Wrapper for `Graph.add_to_collections()` using the default graph.

[`all_variables(...)`](./tf/all_variables.md): See <a href="./tf/global_variables.md"><code>tf.global_variables</code></a>. (deprecated)

[`angle(...)`](./tf/math/angle.md): Returns the element-wise argument of a complex (or real) tensor.

[`arg_max(...)`](./tf/arg_max.md): Returns the index with the largest value across dimensions of a tensor. (deprecated)

[`arg_min(...)`](./tf/arg_min.md): Returns the index with the smallest value across dimensions of a tensor. (deprecated)

[`argmax(...)`](./tf/math/argmax.md): Returns the index with the largest value across axes of a tensor. (deprecated arguments)

[`argmin(...)`](./tf/math/argmin.md): Returns the index with the smallest value across axes of a tensor. (deprecated arguments)

[`as_dtype(...)`](./tf/dtypes/as_dtype.md): Converts the given `type_value` to a `DType`.

[`as_string(...)`](./tf/dtypes/as_string.md): Converts each entry in the given tensor to strings.  Supports many numeric

[`asin(...)`](./tf/math/asin.md): Computes asin of x element-wise.

[`asinh(...)`](./tf/math/asinh.md): Computes inverse hyperbolic sine of x element-wise.

[`assert_equal(...)`](./tf/debugging/assert_equal.md): Assert the condition `x == y` holds element-wise.

[`assert_greater(...)`](./tf/debugging/assert_greater.md): Assert the condition `x > y` holds element-wise.

[`assert_greater_equal(...)`](./tf/debugging/assert_greater_equal.md): Assert the condition `x >= y` holds element-wise.

[`assert_integer(...)`](./tf/debugging/assert_integer.md): Assert that `x` is of integer dtype.

[`assert_less(...)`](./tf/debugging/assert_less.md): Assert the condition `x < y` holds element-wise.

[`assert_less_equal(...)`](./tf/debugging/assert_less_equal.md): Assert the condition `x <= y` holds element-wise.

[`assert_near(...)`](./tf/debugging/assert_near.md): Assert the condition `x` and `y` are close element-wise.

[`assert_negative(...)`](./tf/debugging/assert_negative.md): Assert the condition `x < 0` holds element-wise.

[`assert_non_negative(...)`](./tf/debugging/assert_non_negative.md): Assert the condition `x >= 0` holds element-wise.

[`assert_non_positive(...)`](./tf/debugging/assert_non_positive.md): Assert the condition `x <= 0` holds element-wise.

[`assert_none_equal(...)`](./tf/debugging/assert_none_equal.md): Assert the condition `x != y` holds for all elements.

[`assert_positive(...)`](./tf/debugging/assert_positive.md): Assert the condition `x > 0` holds element-wise.

[`assert_proper_iterable(...)`](./tf/debugging/assert_proper_iterable.md): Static assert that values is a "proper" iterable.

[`assert_rank(...)`](./tf/debugging/assert_rank.md): Assert `x` has rank equal to `rank`.

[`assert_rank_at_least(...)`](./tf/debugging/assert_rank_at_least.md): Assert `x` has rank equal to `rank` or higher.

[`assert_rank_in(...)`](./tf/debugging/assert_rank_in.md): Assert `x` has rank in `ranks`.

[`assert_same_float_dtype(...)`](./tf/debugging/assert_same_float_dtype.md): Validate and return float type based on `tensors` and `dtype`.

[`assert_scalar(...)`](./tf/debugging/assert_scalar.md)

[`assert_type(...)`](./tf/debugging/assert_type.md): Statically asserts that the given `Tensor` is of the specified type.

[`assert_variables_initialized(...)`](./tf/assert_variables_initialized.md): Returns an Op to check if variables are initialized.

[`assign(...)`](./tf/assign.md): Update 'ref' by assigning 'value' to it.

[`assign_add(...)`](./tf/assign_add.md): Update 'ref' by adding 'value' to it.

[`assign_sub(...)`](./tf/assign_sub.md): Update 'ref' by subtracting 'value' from it.

[`atan(...)`](./tf/math/atan.md): Computes atan of x element-wise.

[`atan2(...)`](./tf/math/atan2.md): Computes arctangent of `y/x` element-wise, respecting signs of the arguments.

[`atanh(...)`](./tf/math/atanh.md): Computes inverse hyperbolic tangent of x element-wise.

[`batch_gather(...)`](./tf/batch_gather.md): Gather slices from `params` according to `indices` with leading batch dims.

[`batch_scatter_update(...)`](./tf/batch_scatter_update.md): Generalization of <a href="./tf/scatter_update.md"><code>tf.scatter_update</code></a> to axis different than 0.

[`batch_to_space(...)`](./tf/batch_to_space.md): BatchToSpace for 4-D tensors of type T.

[`batch_to_space_nd(...)`](./tf/batch_to_space_nd.md): BatchToSpace for N-D tensors of type T.

[`betainc(...)`](./tf/math/betainc.md): Compute the regularized incomplete beta integral \\(I_x(a, b)\\).

[`bincount(...)`](./tf/math/bincount.md): Counts the number of occurrences of each value in an integer array.

[`bitcast(...)`](./tf/bitcast.md): Bitcasts a tensor from one type to another without copying data.

[`boolean_mask(...)`](./tf/boolean_mask.md): Apply boolean mask to tensor.  Numpy equivalent is `tensor[mask]`.

[`broadcast_dynamic_shape(...)`](./tf/broadcast_dynamic_shape.md): Returns the broadcasted dynamic shape between `shape_x` and `shape_y`.

[`broadcast_static_shape(...)`](./tf/broadcast_static_shape.md): Returns the broadcasted static shape between `shape_x` and `shape_y`.

[`broadcast_to(...)`](./tf/broadcast_to.md): Broadcast an array for a compatible shape.

[`case(...)`](./tf/case.md): Create a case operation.

[`cast(...)`](./tf/dtypes/cast.md): Casts a tensor to a new type.

[`ceil(...)`](./tf/math/ceil.md): Returns element-wise smallest integer not less than x.

[`check_numerics(...)`](./tf/debugging/check_numerics.md): Checks a tensor for NaN and Inf values.

[`cholesky(...)`](./tf/linalg/cholesky.md): Computes the Cholesky decomposition of one or more square matrices.

[`cholesky_solve(...)`](./tf/linalg/cholesky_solve.md): Solves systems of linear eqns `A X = RHS`, given Cholesky factorizations.

[`clip_by_average_norm(...)`](./tf/clip_by_average_norm.md): Clips tensor values to a maximum average L2-norm.

[`clip_by_global_norm(...)`](./tf/clip_by_global_norm.md): Clips values of multiple tensors by the ratio of the sum of their norms.

[`clip_by_norm(...)`](./tf/clip_by_norm.md): Clips tensor values to a maximum L2-norm.

[`clip_by_value(...)`](./tf/clip_by_value.md): Clips tensor values to a specified min and max.

[`colocate_with(...)`](./tf/colocate_with.md)

[`complex(...)`](./tf/dtypes/complex.md): Converts two real numbers to a complex number.

[`concat(...)`](./tf/concat.md): Concatenates tensors along one dimension.

[`cond(...)`](./tf/cond.md): Return `true_fn()` if the predicate `pred` is true else `false_fn()`. (deprecated arguments)

[`confusion_matrix(...)`](./tf/confusion_matrix.md): Computes the confusion matrix from predictions and labels.

[`conj(...)`](./tf/math/conj.md): Returns the complex conjugate of a complex number.

[`constant(...)`](./tf/constant.md): Creates a constant tensor.

[`container(...)`](./tf/container.md): Wrapper for `Graph.container()` using the default graph.

[`control_dependencies(...)`](./tf/control_dependencies.md): Wrapper for `Graph.control_dependencies()` using the default graph.

[`convert_to_tensor(...)`](./tf/convert_to_tensor.md): Converts the given `value` to a `Tensor`.

[`convert_to_tensor_or_indexed_slices(...)`](./tf/convert_to_tensor_or_indexed_slices.md): Converts the given object to a `Tensor` or an `IndexedSlices`.

[`convert_to_tensor_or_sparse_tensor(...)`](./tf/convert_to_tensor_or_sparse_tensor.md): Converts value to a `SparseTensor` or `Tensor`.

[`cos(...)`](./tf/math/cos.md): Computes cos of x element-wise.

[`cosh(...)`](./tf/math/cosh.md): Computes hyperbolic cosine of x element-wise.

[`count_nonzero(...)`](./tf/math/count_nonzero.md): Computes number of nonzero elements across dimensions of a tensor. (deprecated arguments)

[`count_up_to(...)`](./tf/count_up_to.md): Increments 'ref' until it reaches 'limit'.

[`create_partitioned_variables(...)`](./tf/create_partitioned_variables.md): Create a list of partitioned variables according to the given `slicing`.

[`cross(...)`](./tf/linalg/cross.md): Compute the pairwise cross product.

[`cumprod(...)`](./tf/math/cumprod.md): Compute the cumulative product of the tensor `x` along `axis`.

[`cumsum(...)`](./tf/math/cumsum.md): Compute the cumulative sum of the tensor `x` along `axis`.

[`custom_gradient(...)`](./tf/custom_gradient.md): Decorator to define a function with a custom gradient.

[`decode_base64(...)`](./tf/io/decode_base64.md): Decode web-safe base64-encoded strings.

[`decode_compressed(...)`](./tf/io/decode_compressed.md): Decompress strings.

[`decode_csv(...)`](./tf/io/decode_csv.md): Convert CSV records to tensors. Each column maps to one tensor.

[`decode_json_example(...)`](./tf/io/decode_json_example.md): Convert JSON-encoded Example records to binary protocol buffer strings.

[`decode_raw(...)`](./tf/io/decode_raw.md): Reinterpret the bytes of a string as a vector of numbers.

[`delete_session_tensor(...)`](./tf/delete_session_tensor.md): Delete the tensor for the given tensor handle.

[`depth_to_space(...)`](./tf/nn/depth_to_space.md): DepthToSpace for tensors of type T.

[`dequantize(...)`](./tf/quantization/dequantize.md): Dequantize the 'input' tensor into a float Tensor.

[`deserialize_many_sparse(...)`](./tf/io/deserialize_many_sparse.md): Deserialize and concatenate `SparseTensors` from a serialized minibatch.

[`device(...)`](./tf/device.md): Wrapper for `Graph.device()` using the default graph.

[`diag(...)`](./tf/linalg/tensor_diag.md): Returns a diagonal tensor with a given diagonal values.

[`diag_part(...)`](./tf/linalg/tensor_diag_part.md): Returns the diagonal part of the tensor.

[`digamma(...)`](./tf/math/digamma.md): Computes Psi, the derivative of Lgamma (the log of the absolute value of

[`disable_resource_variables(...)`](./tf/disable_resource_variables.md): Opts out of resource variables. (deprecated)

[`div(...)`](./tf/div.md): Divides x / y elementwise (using Python 2 division operator semantics).

[`div_no_nan(...)`](./tf/div_no_nan.md): Computes an unsafe divide which returns 0 if the y is zero.

[`divide(...)`](./tf/math/divide.md): Computes Python style division of `x` by `y`.

[`dynamic_partition(...)`](./tf/dynamic_partition.md): Partitions `data` into `num_partitions` tensors using indices from `partitions`.

[`dynamic_stitch(...)`](./tf/dynamic_stitch.md): Interleave the values from the `data` tensors into a single tensor.

[`edit_distance(...)`](./tf/edit_distance.md): Computes the Levenshtein distance between sequences.

[`einsum(...)`](./tf/einsum.md): A generalized contraction between tensors of arbitrary dimension.

[`enable_eager_execution(...)`](./tf/enable_eager_execution.md): Enables eager execution for the lifetime of this program.

[`enable_resource_variables(...)`](./tf/enable_resource_variables.md): Creates resource variables by default.

[`encode_base64(...)`](./tf/io/encode_base64.md): Encode strings into web-safe base64 format.

[`ensure_shape(...)`](./tf/ensure_shape.md): Updates the shape of a tensor and checks at runtime that the shape holds.

[`equal(...)`](./tf/math/equal.md): Returns the truth value of (x == y) element-wise.

[`erf(...)`](./tf/math/erf.md): Computes the Gauss error function of `x` element-wise.

[`erfc(...)`](./tf/math/erfc.md): Computes the complementary error function of `x` element-wise.

[`executing_eagerly(...)`](./tf/executing_eagerly.md): Returns True if the current thread has eager execution enabled.

[`exp(...)`](./tf/math/exp.md): Computes exponential of x element-wise.  \\(y = e^x\\).

[`expand_dims(...)`](./tf/expand_dims.md): Inserts a dimension of 1 into a tensor's shape. (deprecated arguments)

[`expm1(...)`](./tf/math/expm1.md): Computes exponential of x - 1 element-wise.

[`extract_image_patches(...)`](./tf/image/extract_image_patches.md): Extract `patches` from `images` and put them in the "depth" output dimension.

[`extract_volume_patches(...)`](./tf/extract_volume_patches.md): Extract `patches` from `input` and put them in the "depth" output

[`eye(...)`](./tf/eye.md): Construct an identity matrix, or a batch of matrices.

[`fake_quant_with_min_max_args(...)`](./tf/quantization/fake_quant_with_min_max_args.md): Fake-quantize the 'inputs' tensor, type float to 'outputs' tensor of same type.

[`fake_quant_with_min_max_args_gradient(...)`](./tf/quantization/fake_quant_with_min_max_args_gradient.md): Compute gradients for a FakeQuantWithMinMaxArgs operation.

[`fake_quant_with_min_max_vars(...)`](./tf/quantization/fake_quant_with_min_max_vars.md): Fake-quantize the 'inputs' tensor of type float via global float scalars `min`

[`fake_quant_with_min_max_vars_gradient(...)`](./tf/quantization/fake_quant_with_min_max_vars_gradient.md): Compute gradients for a FakeQuantWithMinMaxVars operation.

[`fake_quant_with_min_max_vars_per_channel(...)`](./tf/quantization/fake_quant_with_min_max_vars_per_channel.md): Fake-quantize the 'inputs' tensor of type float and one of the shapes: `[d]`,

[`fake_quant_with_min_max_vars_per_channel_gradient(...)`](./tf/quantization/fake_quant_with_min_max_vars_per_channel_gradient.md): Compute gradients for a FakeQuantWithMinMaxVarsPerChannel operation.

[`fft(...)`](./tf/spectral/fft.md): Fast Fourier transform.

[`fft2d(...)`](./tf/spectral/fft2d.md): 2D fast Fourier transform.

[`fft3d(...)`](./tf/spectral/fft3d.md): 3D fast Fourier transform.

[`fill(...)`](./tf/fill.md): Creates a tensor filled with a scalar value.

[`fixed_size_partitioner(...)`](./tf/fixed_size_partitioner.md): Partitioner to specify a fixed number of shards along given axis.

[`floor(...)`](./tf/math/floor.md): Returns element-wise largest integer not greater than x.

[`floor_div(...)`](./tf/floor_div.md): Returns x // y element-wise.

[`floordiv(...)`](./tf/math/floordiv.md): Divides `x / y` elementwise, rounding toward the most negative integer.

[`floormod(...)`](./tf/floormod.md): Returns element-wise remainder of division. When `x < 0` xor `y < 0` is

[`foldl(...)`](./tf/foldl.md): foldl on the list of tensors unpacked from `elems` on dimension 0.

[`foldr(...)`](./tf/foldr.md): foldr on the list of tensors unpacked from `elems` on dimension 0.

[`gather(...)`](./tf/gather.md): Gather slices from `params` axis `axis` according to `indices`.

[`gather_nd(...)`](./tf/gather_nd.md): Gather slices from `params` into a Tensor with shape specified by `indices`.

[`get_collection(...)`](./tf/get_collection.md): Wrapper for `Graph.get_collection()` using the default graph.

[`get_collection_ref(...)`](./tf/get_collection_ref.md): Wrapper for `Graph.get_collection_ref()` using the default graph.

[`get_default_graph(...)`](./tf/get_default_graph.md): Returns the default graph for the current thread.

[`get_default_session(...)`](./tf/get_default_session.md): Returns the default session for the current thread.

[`get_local_variable(...)`](./tf/get_local_variable.md): Gets an existing *local* variable or creates a new one.

[`get_seed(...)`](./tf/random/get_seed.md): Returns the local seeds an operation should use given an op-specific seed.

[`get_session_handle(...)`](./tf/get_session_handle.md): Return the handle of `data`.

[`get_session_tensor(...)`](./tf/get_session_tensor.md): Get the tensor of type `dtype` by feeding a tensor handle.

[`get_variable(...)`](./tf/get_variable.md): Gets an existing variable with these parameters or create a new one.

[`get_variable_scope(...)`](./tf/get_variable_scope.md): Returns the current variable scope.

[`global_norm(...)`](./tf/linalg/global_norm.md): Computes the global norm of multiple tensors.

[`global_variables(...)`](./tf/global_variables.md): Returns global variables.

[`global_variables_initializer(...)`](./tf/initializers/global_variables.md): Returns an Op that initializes global variables.

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

[`ifft(...)`](./tf/spectral/ifft.md): Inverse fast Fourier transform.

[`ifft2d(...)`](./tf/spectral/ifft2d.md): Inverse 2D fast Fourier transform.

[`ifft3d(...)`](./tf/spectral/ifft3d.md): Inverse 3D fast Fourier transform.

[`igamma(...)`](./tf/math/igamma.md): Compute the lower regularized incomplete Gamma function `P(a, x)`.

[`igammac(...)`](./tf/math/igammac.md): Compute the upper regularized incomplete Gamma function `Q(a, x)`.

[`imag(...)`](./tf/math/imag.md): Returns the imaginary part of a complex (or real) tensor.

[`import_graph_def(...)`](./tf/graph_util/import_graph_def.md): Imports the graph from `graph_def` into the current default `Graph`. (deprecated arguments)

[`init_scope(...)`](./tf/init_scope.md): A context manager that lifts ops out of control-flow scopes and function-building graphs.

[`initialize_all_tables(...)`](./tf/initialize_all_tables.md): Returns an Op that initializes all tables of the default graph. (deprecated)

[`initialize_all_variables(...)`](./tf/initialize_all_variables.md): See <a href="./tf/initializers/global_variables.md"><code>tf.global_variables_initializer</code></a>. (deprecated)

[`initialize_local_variables(...)`](./tf/initialize_local_variables.md): See <a href="./tf/initializers/local_variables.md"><code>tf.local_variables_initializer</code></a>. (deprecated)

[`initialize_variables(...)`](./tf/initialize_variables.md): See <a href="./tf/initializers/variables.md"><code>tf.variables_initializer</code></a>. (deprecated)

[`invert_permutation(...)`](./tf/math/invert_permutation.md): Computes the inverse permutation of a tensor.

[`is_finite(...)`](./tf/debugging/is_finite.md): Returns which elements of x are finite.

[`is_inf(...)`](./tf/debugging/is_inf.md): Returns which elements of x are Inf.

[`is_nan(...)`](./tf/debugging/is_nan.md): Returns which elements of x are NaN.

[`is_non_decreasing(...)`](./tf/debugging/is_non_decreasing.md): Returns `True` if `x` is non-decreasing.

[`is_numeric_tensor(...)`](./tf/debugging/is_numeric_tensor.md)

[`is_strictly_increasing(...)`](./tf/debugging/is_strictly_increasing.md): Returns `True` if `x` is strictly increasing.

[`is_variable_initialized(...)`](./tf/is_variable_initialized.md): Tests if a variable has been initialized.

[`lbeta(...)`](./tf/math/lbeta.md): Computes \\(ln(|Beta(x)|)\\), reducing along the last dimension.

[`less(...)`](./tf/math/less.md): Returns the truth value of (x < y) element-wise.

[`less_equal(...)`](./tf/math/less_equal.md): Returns the truth value of (x <= y) element-wise.

[`lgamma(...)`](./tf/math/lgamma.md): Computes the log of the absolute value of `Gamma(x)` element-wise.

[`lin_space(...)`](./tf/lin_space.md): Generates values in an interval.

[`linspace(...)`](./tf/lin_space.md): Generates values in an interval.

[`load_file_system_library(...)`](./tf/load_file_system_library.md): Loads a TensorFlow plugin, containing file system implementation.

[`load_library(...)`](./tf/load_library.md): Loads a TensorFlow plugin.

[`load_op_library(...)`](./tf/load_op_library.md): Loads a TensorFlow plugin, containing custom ops and kernels.

[`local_variables(...)`](./tf/local_variables.md): Returns local variables.

[`local_variables_initializer(...)`](./tf/initializers/local_variables.md): Returns an Op that initializes all local variables.

[`log(...)`](./tf/math/log.md): Computes natural logarithm of x element-wise.

[`log1p(...)`](./tf/math/log1p.md): Computes natural logarithm of (1 + x) element-wise.

[`log_sigmoid(...)`](./tf/math/log_sigmoid.md): Computes log sigmoid of `x` element-wise.

[`logical_and(...)`](./tf/math/logical_and.md): Returns the truth value of x AND y element-wise.

[`logical_not(...)`](./tf/math/logical_not.md): Returns the truth value of NOT x element-wise.

[`logical_or(...)`](./tf/math/logical_or.md): Returns the truth value of x OR y element-wise.

[`logical_xor(...)`](./tf/math/logical_xor.md): x ^ y = (x | y) & ~(x & y).

[`make_ndarray(...)`](./tf/make_ndarray.md): Create a numpy ndarray from a tensor.

[`make_template(...)`](./tf/make_template.md): Given an arbitrary function, wrap it so that it does variable sharing.

[`make_tensor_proto(...)`](./tf/make_tensor_proto.md): Create a TensorProto.

[`map_fn(...)`](./tf/map_fn.md): map on the list of tensors unpacked from `elems` on dimension 0.

[`matching_files(...)`](./tf/io/matching_files.md): Returns the set of files matching one or more glob patterns.

[`matmul(...)`](./tf/linalg/matmul.md): Multiplies matrix `a` by matrix `b`, producing `a` * `b`.

[`matrix_band_part(...)`](./tf/linalg/band_part.md): Copy a tensor setting everything outside a central band in each innermost matrix

[`matrix_determinant(...)`](./tf/linalg/det.md): Computes the determinant of one or more square matrices.

[`matrix_diag(...)`](./tf/linalg/diag.md): Returns a batched diagonal tensor with a given batched diagonal values.

[`matrix_diag_part(...)`](./tf/linalg/diag_part.md): Returns the batched diagonal part of a batched tensor.

[`matrix_inverse(...)`](./tf/linalg/inv.md): Computes the inverse of one or more square invertible matrices or their

[`matrix_set_diag(...)`](./tf/linalg/set_diag.md): Returns a batched matrix tensor with new batched diagonal values.

[`matrix_solve(...)`](./tf/linalg/solve.md): Solves systems of linear equations.

[`matrix_solve_ls(...)`](./tf/linalg/lstsq.md): Solves one or more linear least-squares problems.

[`matrix_transpose(...)`](./tf/linalg/transpose.md): Transposes last two dimensions of tensor `a`.

[`matrix_triangular_solve(...)`](./tf/linalg/triangular_solve.md): Solves systems of linear equations with upper or lower triangular matrices by

[`maximum(...)`](./tf/math/maximum.md): Returns the max of x and y (i.e. x > y ? x : y) element-wise.

[`meshgrid(...)`](./tf/meshgrid.md): Broadcasts parameters for evaluation on an N-D grid.

[`min_max_variable_partitioner(...)`](./tf/min_max_variable_partitioner.md): Partitioner to allocate minimum size per slice.

[`minimum(...)`](./tf/math/minimum.md): Returns the min of x and y (i.e. x < y ? x : y) element-wise.

[`mod(...)`](./tf/floormod.md): Returns element-wise remainder of division. When `x < 0` xor `y < 0` is

[`model_variables(...)`](./tf/model_variables.md): Returns all variables in the MODEL_VARIABLES collection.

[`moving_average_variables(...)`](./tf/moving_average_variables.md): Returns all variables that maintain their moving averages.

[`multinomial(...)`](./tf/random/multinomial.md): Draws samples from a multinomial distribution.

[`multiply(...)`](./tf/math/multiply.md): Returns x * y element-wise.

[`negative(...)`](./tf/math/negative.md): Computes numerical negative value element-wise.

[`no_op(...)`](./tf/no_op.md): Does nothing. Only useful as a placeholder for control edges.

[`no_regularizer(...)`](./tf/no_regularizer.md): Use this function to prevent regularization of variables.

[`norm(...)`](./tf/norm.md): Computes the norm of vectors, matrices, and tensors. (deprecated arguments)

[`not_equal(...)`](./tf/math/not_equal.md): Returns the truth value of (x != y) element-wise.

[`one_hot(...)`](./tf/one_hot.md): Returns a one-hot tensor.

[`ones(...)`](./tf/ones.md): Creates a tensor with all elements set to 1.

[`ones_like(...)`](./tf/ones_like.md): Creates a tensor with all elements set to 1.

[`op_scope(...)`](./tf/op_scope.md): DEPRECATED. Same as name_scope above, just different argument order.

[`pad(...)`](./tf/pad.md): Pads a tensor.

[`parallel_stack(...)`](./tf/parallel_stack.md): Stacks a list of rank-`R` tensors into one rank-`(R+1)` tensor in parallel.

[`parse_example(...)`](./tf/io/parse_example.md): Parses `Example` protos into a `dict` of tensors.

[`parse_single_example(...)`](./tf/io/parse_single_example.md): Parses a single `Example` proto.

[`parse_single_sequence_example(...)`](./tf/io/parse_single_sequence_example.md): Parses a single `SequenceExample` proto.

[`parse_tensor(...)`](./tf/io/parse_tensor.md): Transforms a serialized tensorflow.TensorProto proto into a Tensor.

[`placeholder(...)`](./tf/placeholder.md): Inserts a placeholder for a tensor that will be always fed.

[`placeholder_with_default(...)`](./tf/placeholder_with_default.md): A placeholder op that passes through `input` when its output is not fed.

[`polygamma(...)`](./tf/math/polygamma.md): Compute the polygamma function \\(\psi^{(n)}(x)\\).

[`pow(...)`](./tf/math/pow.md): Computes the power of one value to another.

[`print(...)`](./tf/print.md): Print the specified inputs.

[`py_func(...)`](./tf/py_func.md): Wraps a python function and uses it as a TensorFlow op.

[`qr(...)`](./tf/linalg/qr.md): Computes the QR decompositions of one or more matrices.

[`quantize(...)`](./tf/quantization/quantize.md): Quantize the 'input' tensor of type float to 'output' tensor of type 'T'.

[`quantize_v2(...)`](./tf/quantize_v2.md): Please use <a href="./tf/quantization/quantize.md"><code>tf.quantize</code></a> instead.

[`quantized_concat(...)`](./tf/quantization/quantized_concat.md): Concatenates quantized tensors along one dimension.

[`random_crop(...)`](./tf/image/random_crop.md): Randomly crops a tensor to a given size.

[`random_gamma(...)`](./tf/random/gamma.md): Draws `shape` samples from each of the given Gamma distribution(s).

[`random_normal(...)`](./tf/random/normal.md): Outputs random values from a normal distribution.

[`random_poisson(...)`](./tf/random/poisson.md): Draws `shape` samples from each of the given Poisson distribution(s).

[`random_shuffle(...)`](./tf/random/shuffle.md): Randomly shuffles a tensor along its first dimension.

[`random_uniform(...)`](./tf/random/uniform.md): Outputs random values from a uniform distribution.

[`range(...)`](./tf/range.md): Creates a sequence of numbers.

[`rank(...)`](./tf/rank.md): Returns the rank of a tensor.

[`read_file(...)`](./tf/io/read_file.md): Reads and outputs the entire contents of the input filename.

[`real(...)`](./tf/math/real.md): Returns the real part of a complex (or real) tensor.

[`realdiv(...)`](./tf/realdiv.md): Returns x / y element-wise for real types.

[`reciprocal(...)`](./tf/math/reciprocal.md): Computes the reciprocal of x element-wise.

[`reduce_all(...)`](./tf/math/reduce_all.md): Computes the "logical and" of elements across dimensions of a tensor. (deprecated arguments)

[`reduce_any(...)`](./tf/math/reduce_any.md): Computes the "logical or" of elements across dimensions of a tensor. (deprecated arguments)

[`reduce_join(...)`](./tf/strings/reduce_join.md): Joins a string Tensor across the given dimensions.

[`reduce_logsumexp(...)`](./tf/math/reduce_logsumexp.md): Computes log(sum(exp(elements across dimensions of a tensor))). (deprecated arguments)

[`reduce_max(...)`](./tf/math/reduce_max.md): Computes the maximum of elements across dimensions of a tensor. (deprecated arguments)

[`reduce_mean(...)`](./tf/math/reduce_mean.md): Computes the mean of elements across dimensions of a tensor. (deprecated arguments)

[`reduce_min(...)`](./tf/math/reduce_min.md): Computes the minimum of elements across dimensions of a tensor. (deprecated arguments)

[`reduce_prod(...)`](./tf/math/reduce_prod.md): Computes the product of elements across dimensions of a tensor. (deprecated arguments)

[`reduce_sum(...)`](./tf/math/reduce_sum.md): Computes the sum of elements across dimensions of a tensor. (deprecated arguments)

[`regex_replace(...)`](./tf/strings/regex_replace.md): Replaces the match of pattern in input with rewrite.

[`register_tensor_conversion_function(...)`](./tf/register_tensor_conversion_function.md): Registers a function for converting objects of `base_type` to `Tensor`.

[`report_uninitialized_variables(...)`](./tf/report_uninitialized_variables.md): Adds ops to list the names of uninitialized variables.

[`required_space_to_batch_paddings(...)`](./tf/required_space_to_batch_paddings.md): Calculate padding required to make block_shape divide input_shape.

[`reset_default_graph(...)`](./tf/reset_default_graph.md): Clears the default graph stack and resets the global default graph.

[`reshape(...)`](./tf/reshape.md): Reshapes a tensor.

[`reverse(...)`](./tf/reverse.md): Reverses specific dimensions of a tensor.

[`reverse_sequence(...)`](./tf/reverse_sequence.md): Reverses variable length slices.

[`reverse_v2(...)`](./tf/reverse.md): Reverses specific dimensions of a tensor.

[`rint(...)`](./tf/math/rint.md): Returns element-wise integer closest to x.

[`roll(...)`](./tf/roll.md): Rolls the elements of a tensor along an axis.

[`round(...)`](./tf/math/round.md): Rounds the values of a tensor to the nearest integer, element-wise.

[`rsqrt(...)`](./tf/math/rsqrt.md): Computes reciprocal of square root of x element-wise.

[`saturate_cast(...)`](./tf/dtypes/saturate_cast.md): Performs a safe saturating cast of `value` to `dtype`.

[`scalar_mul(...)`](./tf/math/scalar_mul.md): Multiplies a scalar times a `Tensor` or `IndexedSlices` object.

[`scan(...)`](./tf/scan.md): scan on the list of tensors unpacked from `elems` on dimension 0.

[`scatter_add(...)`](./tf/scatter_add.md): Adds sparse updates to the variable referenced by `resource`.

[`scatter_div(...)`](./tf/scatter_div.md): Divides a variable reference by sparse updates.

[`scatter_max(...)`](./tf/scatter_max.md): Reduces sparse updates into a variable reference using the `max` operation.

[`scatter_min(...)`](./tf/scatter_min.md): Reduces sparse updates into a variable reference using the `min` operation.

[`scatter_mul(...)`](./tf/scatter_mul.md): Multiplies sparse updates into a variable reference.

[`scatter_nd(...)`](./tf/scatter_nd.md): Scatter `updates` into a new tensor according to `indices`.

[`scatter_nd_add(...)`](./tf/scatter_nd_add.md): Applies sparse addition to individual values or slices in a Variable.

[`scatter_nd_sub(...)`](./tf/scatter_nd_sub.md): Applies sparse subtraction to individual values or slices in a Variable.

[`scatter_nd_update(...)`](./tf/scatter_nd_update.md): Applies sparse `updates` to individual values or slices in a Variable.

[`scatter_sub(...)`](./tf/scatter_sub.md): Subtracts sparse updates to a variable reference.

[`scatter_update(...)`](./tf/scatter_update.md): Applies sparse updates to a variable reference.

[`searchsorted(...)`](./tf/searchsorted.md): Searches input tensor for values on the innermost dimension.

[`segment_max(...)`](./tf/math/segment_max.md): Computes the maximum along segments of a tensor.

[`segment_mean(...)`](./tf/math/segment_mean.md): Computes the mean along segments of a tensor.

[`segment_min(...)`](./tf/math/segment_min.md): Computes the minimum along segments of a tensor.

[`segment_prod(...)`](./tf/math/segment_prod.md): Computes the product along segments of a tensor.

[`segment_sum(...)`](./tf/math/segment_sum.md): Computes the sum along segments of a tensor.

[`self_adjoint_eig(...)`](./tf/linalg/eigh.md): Computes the eigen decomposition of a batch of self-adjoint matrices.

[`self_adjoint_eigvals(...)`](./tf/linalg/eigvalsh.md): Computes the eigenvalues of one or more self-adjoint matrices.

[`sequence_mask(...)`](./tf/sequence_mask.md): Returns a mask tensor representing the first N positions of each cell.

[`serialize_many_sparse(...)`](./tf/io/serialize_many_sparse.md): Serialize `N`-minibatch `SparseTensor` into an `[N, 3]` `Tensor`.

[`serialize_sparse(...)`](./tf/io/serialize_sparse.md): Serialize a `SparseTensor` into a 3-vector (1-D `Tensor`) object.

[`serialize_tensor(...)`](./tf/serialize_tensor.md): Transforms a Tensor into a serialized TensorProto proto.

[`set_random_seed(...)`](./tf/random/set_random_seed.md): Sets the graph-level random seed.

[`setdiff1d(...)`](./tf/setdiff1d.md): Computes the difference between two lists of numbers or strings.

[`shape(...)`](./tf/shape.md): Returns the shape of a tensor.

[`shape_n(...)`](./tf/shape_n.md): Returns shape of tensors.

[`sigmoid(...)`](./tf/math/sigmoid.md): Computes sigmoid of `x` element-wise.

[`sign(...)`](./tf/math/sign.md): Returns an element-wise indication of the sign of a number.

[`sin(...)`](./tf/math/sin.md): Computes sin of x element-wise.

[`sinh(...)`](./tf/math/sinh.md): Computes hyperbolic sine of x element-wise.

[`size(...)`](./tf/size.md): Returns the size of a tensor.

[`slice(...)`](./tf/slice.md): Extracts a slice from a tensor.

[`space_to_batch(...)`](./tf/nn/space_to_batch.md): SpaceToBatch for 4-D tensors of type T.

[`space_to_batch_nd(...)`](./tf/space_to_batch_nd.md): SpaceToBatch for N-D tensors of type T.

[`space_to_depth(...)`](./tf/nn/space_to_depth.md): SpaceToDepth for tensors of type T.

[`sparse_add(...)`](./tf/sparse/add.md): Adds two tensors, at least one of each is a `SparseTensor`.

[`sparse_concat(...)`](./tf/sparse/concat.md): Concatenates a list of `SparseTensor` along the specified dimension. (deprecated arguments)

[`sparse_fill_empty_rows(...)`](./tf/sparse/fill_empty_rows.md): Fills empty rows in the input 2-D `SparseTensor` with a default value.

[`sparse_mask(...)`](./tf/sparse/mask.md): Masks elements of `IndexedSlices`.

[`sparse_matmul(...)`](./tf/sparse_matmul.md): Multiply matrix "a" by matrix "b".

[`sparse_maximum(...)`](./tf/sparse/maximum.md): Returns the element-wise max of two SparseTensors.

[`sparse_merge(...)`](./tf/sparse/merge.md): Combines a batch of feature ids and values into a single `SparseTensor`.

[`sparse_minimum(...)`](./tf/sparse/minimum.md): Returns the element-wise min of two SparseTensors.

[`sparse_placeholder(...)`](./tf/sparse/placeholder.md): Inserts a placeholder for a sparse tensor that will be always fed.

[`sparse_reduce_max(...)`](./tf/sparse/reduce_max.md): Computes the max of elements across dimensions of a SparseTensor. (deprecated arguments)

[`sparse_reduce_max_sparse(...)`](./tf/sparse/reduce_max_sparse.md): Computes the max of elements across dimensions of a SparseTensor. (deprecated arguments)

[`sparse_reduce_sum(...)`](./tf/sparse/reduce_sum.md): Computes the sum of elements across dimensions of a SparseTensor. (deprecated arguments)

[`sparse_reduce_sum_sparse(...)`](./tf/sparse/reduce_sum_sparse.md): Computes the sum of elements across dimensions of a SparseTensor. (deprecated arguments)

[`sparse_reorder(...)`](./tf/sparse/reorder.md): Reorders a `SparseTensor` into the canonical, row-major ordering.

[`sparse_reset_shape(...)`](./tf/sparse/reset_shape.md): Resets the shape of a `SparseTensor` with indices and values unchanged.

[`sparse_reshape(...)`](./tf/sparse/reshape.md): Reshapes a `SparseTensor` to represent values in a new dense shape.

[`sparse_retain(...)`](./tf/sparse/retain.md): Retains specified non-empty values within a `SparseTensor`.

[`sparse_segment_mean(...)`](./tf/sparse/segment_mean.md): Computes the mean along sparse segments of a tensor.

[`sparse_segment_sqrt_n(...)`](./tf/sparse/segment_sqrt_n.md): Computes the sum along sparse segments of a tensor divided by the sqrt(N).

[`sparse_segment_sum(...)`](./tf/sparse/segment_sum.md): Computes the sum along sparse segments of a tensor.

[`sparse_slice(...)`](./tf/sparse/slice.md): Slice a `SparseTensor` based on the `start` and `size.

[`sparse_softmax(...)`](./tf/sparse/softmax.md): Applies softmax to a batched N-D `SparseTensor`.

[`sparse_split(...)`](./tf/sparse/split.md): Split a `SparseTensor` into `num_split` tensors along `axis`. (deprecated arguments)

[`sparse_tensor_dense_matmul(...)`](./tf/sparse/matmul.md): Multiply SparseTensor (of rank 2) "A" by dense matrix "B".

[`sparse_tensor_to_dense(...)`](./tf/sparse/to_dense.md): Converts a `SparseTensor` into a dense tensor.

[`sparse_to_dense(...)`](./tf/sparse_to_dense.md): Converts a sparse representation into a dense tensor. (deprecated)

[`sparse_to_indicator(...)`](./tf/sparse/to_indicator.md): Converts a `SparseTensor` of ids into a dense bool indicator tensor.

[`sparse_transpose(...)`](./tf/sparse/transpose.md): Transposes a `SparseTensor`

[`split(...)`](./tf/split.md): Splits a tensor into sub tensors.

[`sqrt(...)`](./tf/math/sqrt.md): Computes square root of x element-wise.

[`square(...)`](./tf/math/square.md): Computes square of x element-wise.

[`squared_difference(...)`](./tf/math/squared_difference.md): Returns (x - y)(x - y) element-wise.

[`squeeze(...)`](./tf/squeeze.md): Removes dimensions of size 1 from the shape of a tensor. (deprecated arguments)

[`stack(...)`](./tf/stack.md): Stacks a list of rank-`R` tensors into one rank-`(R+1)` tensor.

[`stop_gradient(...)`](./tf/stop_gradient.md): Stops gradient computation.

[`strided_slice(...)`](./tf/strided_slice.md): Extracts a strided slice of a tensor (generalized python array indexing).

[`string_join(...)`](./tf/strings/join.md): Joins the strings in the given list of string tensors into one tensor;

[`string_split(...)`](./tf/string_split.md): Split elements of `source` based on `delimiter` into a `SparseTensor`.

[`string_strip(...)`](./tf/strings/strip.md): Strip leading and trailing whitespaces from the Tensor.

[`string_to_hash_bucket(...)`](./tf/strings/to_hash_bucket.md): Converts each string in the input Tensor to its hash mod by a number of buckets.

[`string_to_hash_bucket_fast(...)`](./tf/strings/to_hash_bucket_fast.md): Converts each string in the input Tensor to its hash mod by a number of buckets.

[`string_to_hash_bucket_strong(...)`](./tf/strings/to_hash_bucket_strong.md): Converts each string in the input Tensor to its hash mod by a number of buckets.

[`string_to_number(...)`](./tf/strings/to_number.md): Converts each string in the input Tensor to the specified numeric type.

[`substr(...)`](./tf/strings/substr.md): Return substrings from `Tensor` of strings.

[`subtract(...)`](./tf/math/subtract.md): Returns x - y element-wise.

[`svd(...)`](./tf/linalg/svd.md): Computes the singular value decompositions of one or more matrices.

[`tables_initializer(...)`](./tf/initializers/tables_initializer.md): Returns an Op that initializes all tables of the default graph.

[`tan(...)`](./tf/math/tan.md): Computes tan of x element-wise.

[`tanh(...)`](./tf/math/tanh.md): Computes hyperbolic tangent of `x` element-wise.

[`tensordot(...)`](./tf/tensordot.md): Tensor contraction of a and b along specified axes.

[`tile(...)`](./tf/tile.md): Constructs a tensor by tiling a given tensor.

[`timestamp(...)`](./tf/timestamp.md): Provides the time since epoch in seconds.

[`to_bfloat16(...)`](./tf/to_bfloat16.md): Casts a tensor to type `bfloat16`.

[`to_complex128(...)`](./tf/to_complex128.md): Casts a tensor to type `complex128`.

[`to_complex64(...)`](./tf/to_complex64.md): Casts a tensor to type `complex64`.

[`to_double(...)`](./tf/to_double.md): Casts a tensor to type `float64`.

[`to_float(...)`](./tf/to_float.md): Casts a tensor to type `float32`.

[`to_int32(...)`](./tf/to_int32.md): Casts a tensor to type `int32`.

[`to_int64(...)`](./tf/to_int64.md): Casts a tensor to type `int64`.

[`trace(...)`](./tf/linalg/trace.md): Compute the trace of a tensor `x`.

[`trainable_variables(...)`](./tf/trainable_variables.md): Returns all variables created with `trainable=True`.

[`transpose(...)`](./tf/transpose.md): Transposes `a`. Permutes the dimensions according to `perm`.

[`truediv(...)`](./tf/math/truediv.md): Divides x / y elementwise (using Python 3 division operator semantics).

[`truncated_normal(...)`](./tf/random/truncated_normal.md): Outputs random values from a truncated normal distribution.

[`truncatediv(...)`](./tf/truncatediv.md): Returns x / y element-wise for integer types.

[`truncatemod(...)`](./tf/truncatemod.md): Returns element-wise remainder of division. This emulates C semantics in that

[`tuple(...)`](./tf/tuple.md): Group tensors together.

[`unique(...)`](./tf/unique.md): Finds unique elements in a 1-D tensor.

[`unique_with_counts(...)`](./tf/unique_with_counts.md): Finds unique elements in a 1-D tensor.

[`unravel_index(...)`](./tf/unravel_index.md): Converts a flat index or array of flat indices into a tuple of

[`unsorted_segment_max(...)`](./tf/math/unsorted_segment_max.md): Computes the maximum along segments of a tensor.

[`unsorted_segment_mean(...)`](./tf/math/unsorted_segment_mean.md): Computes the mean along segments of a tensor.

[`unsorted_segment_min(...)`](./tf/math/unsorted_segment_min.md): Computes the minimum along segments of a tensor.

[`unsorted_segment_prod(...)`](./tf/math/unsorted_segment_prod.md): Computes the product along segments of a tensor.

[`unsorted_segment_sqrt_n(...)`](./tf/math/unsorted_segment_sqrt_n.md): Computes the sum along segments of a tensor divided by the sqrt(N).

[`unsorted_segment_sum(...)`](./tf/math/unsorted_segment_sum.md): Computes the sum along segments of a tensor.

[`unstack(...)`](./tf/unstack.md): Unpacks the given dimension of a rank-`R` tensor into rank-`(R-1)` tensors.

[`variable_axis_size_partitioner(...)`](./tf/variable_axis_size_partitioner.md): Get a partitioner for VariableScope to keep shards below `max_shard_bytes`.

[`variable_creator_scope(...)`](./tf/variable_creator_scope.md): Scope which defines a variable creation function to be used by variable().

[`variable_op_scope(...)`](./tf/variable_op_scope.md): Deprecated: context manager for defining an op that creates variables.

[`variables_initializer(...)`](./tf/initializers/variables.md): Returns an Op that initializes a list of variables.

[`verify_tensor_all_finite(...)`](./tf/debugging/assert_all_finite.md): Assert that the tensor does not contain any NaN's or Inf's.

[`where(...)`](./tf/where.md): Return the elements, either from `x` or `y`, depending on the `condition`.

[`while_loop(...)`](./tf/while_loop.md): Repeat `body` while the condition `cond` is true.

[`write_file(...)`](./tf/io/write_file.md): Writes contents to the file at input filename. Creates file and recursively

[`zeros(...)`](./tf/zeros.md): Creates a tensor with all elements set to zero.

[`zeros_like(...)`](./tf/zeros_like.md): Creates a tensor with all elements set to zero.

[`zeta(...)`](./tf/math/zeta.md): Compute the Hurwitz zeta function \\(\zeta(x, q)\\).

## Other Members

<h3 id="AUTO_REUSE"><code>AUTO_REUSE</code></h3>

<h3 id="COMPILER_VERSION"><code>COMPILER_VERSION</code></h3>

<h3 id="CXX11_ABI_FLAG"><code>CXX11_ABI_FLAG</code></h3>

<h3 id="GIT_VERSION"><code>GIT_VERSION</code></h3>

<h3 id="GRAPH_DEF_VERSION"><code>GRAPH_DEF_VERSION</code></h3>

<h3 id="GRAPH_DEF_VERSION_MIN_CONSUMER"><code>GRAPH_DEF_VERSION_MIN_CONSUMER</code></h3>

<h3 id="GRAPH_DEF_VERSION_MIN_PRODUCER"><code>GRAPH_DEF_VERSION_MIN_PRODUCER</code></h3>

<h3 id="MONOLITHIC_BUILD"><code>MONOLITHIC_BUILD</code></h3>

<h3 id="QUANTIZED_DTYPES"><code>QUANTIZED_DTYPES</code></h3>

<h3 id="VERSION"><code>VERSION</code></h3>

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

