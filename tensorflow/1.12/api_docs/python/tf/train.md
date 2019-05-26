<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.train



Defined in [`tensorflow/_api/v1/train/__init__.py`](/code/stable/tensorflow/_api/v1/train/__init__.py).

Support for training models.

See the [Training](https://tensorflow.org/api_guides/python/train) guide.

## Modules

[`queue_runner`](../tf/train/queue_runner.md) module: Public API for tf.train.queue_runner namespace.

## Classes

[`class AdadeltaOptimizer`](../tf/train/AdadeltaOptimizer.md): Optimizer that implements the Adadelta algorithm.

[`class AdagradDAOptimizer`](../tf/train/AdagradDAOptimizer.md): Adagrad Dual Averaging algorithm for sparse linear models.

[`class AdagradOptimizer`](../tf/train/AdagradOptimizer.md): Optimizer that implements the Adagrad algorithm.

[`class AdamOptimizer`](../tf/train/AdamOptimizer.md): Optimizer that implements the Adam algorithm.

[`class BytesList`](../tf/train/BytesList.md): A ProtocolMessage

[`class Checkpoint`](../tf/train/Checkpoint.md): Groups checkpointable objects, saving and restoring them.

[`class CheckpointSaverHook`](../tf/train/CheckpointSaverHook.md): Saves checkpoints every N steps or seconds.

[`class CheckpointSaverListener`](../tf/train/CheckpointSaverListener.md): Interface for listeners that take action before or after checkpoint save.

[`class ChiefSessionCreator`](../tf/train/ChiefSessionCreator.md): Creates a tf.Session for a chief.

[`class ClusterDef`](../tf/train/ClusterDef.md): A ProtocolMessage

[`class ClusterSpec`](../tf/train/ClusterSpec.md): Represents a cluster as a set of "tasks", organized into "jobs".

[`class Coordinator`](../tf/train/Coordinator.md): A coordinator for threads.

[`class Example`](../tf/train/Example.md): A ProtocolMessage

[`class ExponentialMovingAverage`](../tf/train/ExponentialMovingAverage.md): Maintains moving averages of variables by employing an exponential decay.

[`class Feature`](../tf/train/Feature.md): A ProtocolMessage

[`class FeatureList`](../tf/train/FeatureList.md): A ProtocolMessage

[`class FeatureLists`](../tf/train/FeatureLists.md): A ProtocolMessage

[`class Features`](../tf/train/Features.md): A ProtocolMessage

[`class FeedFnHook`](../tf/train/FeedFnHook.md): Runs `feed_fn` and sets the `feed_dict` accordingly.

[`class FinalOpsHook`](../tf/train/FinalOpsHook.md): A hook which evaluates `Tensors` at the end of a session.

[`class FloatList`](../tf/train/FloatList.md): A ProtocolMessage

[`class FtrlOptimizer`](../tf/train/FtrlOptimizer.md): Optimizer that implements the FTRL algorithm.

[`class GlobalStepWaiterHook`](../tf/train/GlobalStepWaiterHook.md): Delays execution until global step reaches `wait_until_step`.

[`class GradientDescentOptimizer`](../tf/train/GradientDescentOptimizer.md): Optimizer that implements the gradient descent algorithm.

[`class Int64List`](../tf/train/Int64List.md): A ProtocolMessage

[`class JobDef`](../tf/train/JobDef.md): A ProtocolMessage

[`class LoggingTensorHook`](../tf/train/LoggingTensorHook.md): Prints the given tensors every N local steps, every N seconds, or at end.

[`class LooperThread`](../tf/train/LooperThread.md): A thread that runs code repeatedly, optionally on a timer.

[`class MomentumOptimizer`](../tf/train/MomentumOptimizer.md): Optimizer that implements the Momentum algorithm.

[`class MonitoredSession`](../tf/train/MonitoredSession.md): Session-like object that handles initialization, recovery and hooks.

[`class NanLossDuringTrainingError`](../tf/train/NanLossDuringTrainingError.md): Unspecified run-time error.

[`class NanTensorHook`](../tf/train/NanTensorHook.md): Monitors the loss tensor and stops training if loss is NaN.

[`class Optimizer`](../tf/train/Optimizer.md): Base class for optimizers.

[`class ProfilerHook`](../tf/train/ProfilerHook.md): Captures CPU/GPU profiling information every N steps or seconds.

[`class ProximalAdagradOptimizer`](../tf/train/ProximalAdagradOptimizer.md): Optimizer that implements the Proximal Adagrad algorithm.

[`class ProximalGradientDescentOptimizer`](../tf/train/ProximalGradientDescentOptimizer.md): Optimizer that implements the proximal gradient descent algorithm.

[`class QueueRunner`](../tf/train/QueueRunner.md): Holds a list of enqueue operations for a queue, each to be run in a thread.

[`class RMSPropOptimizer`](../tf/train/RMSPropOptimizer.md): Optimizer that implements the RMSProp algorithm.

[`class Saver`](../tf/train/Saver.md): Saves and restores variables.

[`class SaverDef`](../tf/train/SaverDef.md): A ProtocolMessage

[`class Scaffold`](../tf/train/Scaffold.md): Structure to create or gather pieces commonly needed to train a model.

[`class SecondOrStepTimer`](../tf/train/SecondOrStepTimer.md): Timer that triggers at most once every N seconds or once every N steps.

[`class SequenceExample`](../tf/train/SequenceExample.md): A ProtocolMessage

[`class Server`](../tf/train/Server.md): An in-process TensorFlow server, for use in distributed training.

[`class ServerDef`](../tf/train/ServerDef.md): A ProtocolMessage

[`class SessionCreator`](../tf/train/SessionCreator.md): A factory for tf.Session.

[`class SessionManager`](../tf/train/SessionManager.md): Training helper that restores from checkpoint and creates session.

[`class SessionRunArgs`](../tf/train/SessionRunArgs.md): Represents arguments to be added to a `Session.run()` call.

[`class SessionRunContext`](../tf/train/SessionRunContext.md): Provides information about the `session.run()` call being made.

[`class SessionRunHook`](../tf/train/SessionRunHook.md): Hook to extend calls to MonitoredSession.run().

[`class SessionRunValues`](../tf/train/SessionRunValues.md): Contains the results of `Session.run()`.

[`class SingularMonitoredSession`](../tf/train/SingularMonitoredSession.md): Session-like object that handles initialization, restoring, and hooks.

[`class StepCounterHook`](../tf/train/StepCounterHook.md): Hook that counts steps per second.

[`class StopAtStepHook`](../tf/train/StopAtStepHook.md): Hook that requests stop at a specified step.

[`class SummarySaverHook`](../tf/train/SummarySaverHook.md): Saves summaries every N steps.

[`class Supervisor`](../tf/train/Supervisor.md): A training helper that checkpoints models and computes summaries.

[`class SyncReplicasOptimizer`](../tf/train/SyncReplicasOptimizer.md): Class to synchronize, aggregate gradients and pass them to the optimizer.

[`class VocabInfo`](../tf/train/VocabInfo.md): Vocabulary information for warm-starting.

[`class WorkerSessionCreator`](../tf/train/WorkerSessionCreator.md): Creates a tf.Session for a worker.

## Functions

[`MonitoredTrainingSession(...)`](../tf/train/MonitoredTrainingSession.md): Creates a `MonitoredSession` for training.

[`NewCheckpointReader(...)`](../tf/train/NewCheckpointReader.md)

[`add_queue_runner(...)`](../tf/train/add_queue_runner.md): Adds a `QueueRunner` to a collection in the graph. (deprecated)

[`assert_global_step(...)`](../tf/train/assert_global_step.md): Asserts `global_step_tensor` is a scalar int `Variable` or `Tensor`.

[`basic_train_loop(...)`](../tf/train/basic_train_loop.md): Basic loop to train a model.

[`batch(...)`](../tf/train/batch.md): Creates batches of tensors in `tensors`. (deprecated)

[`batch_join(...)`](../tf/train/batch_join.md): Runs a list of tensors to fill a queue to create batches of examples. (deprecated)

[`checkpoint_exists(...)`](../tf/train/checkpoint_exists.md): Checks whether a V1 or V2 checkpoint exists with the specified prefix.

[`cosine_decay(...)`](../tf/train/cosine_decay.md): Applies cosine decay to the learning rate.

[`cosine_decay_restarts(...)`](../tf/train/cosine_decay_restarts.md): Applies cosine decay with restarts to the learning rate.

[`create_global_step(...)`](../tf/train/create_global_step.md): Create global step tensor in graph.

[`do_quantize_training_on_graphdef(...)`](../tf/train/do_quantize_training_on_graphdef.md): A general quantization scheme is being developed in <a href="../tf/contrib/quantize.md"><code>tf.contrib.quantize</code></a>. (deprecated)

[`exponential_decay(...)`](../tf/train/exponential_decay.md): Applies exponential decay to the learning rate.

[`export_meta_graph(...)`](../tf/train/export_meta_graph.md): Returns `MetaGraphDef` proto. Optionally writes it to filename.

[`generate_checkpoint_state_proto(...)`](../tf/train/generate_checkpoint_state_proto.md): Generates a checkpoint state proto.

[`get_checkpoint_mtimes(...)`](../tf/train/get_checkpoint_mtimes.md): Returns the mtimes (modification timestamps) of the checkpoints.

[`get_checkpoint_state(...)`](../tf/train/get_checkpoint_state.md): Returns CheckpointState proto from the "checkpoint" file.

[`get_global_step(...)`](../tf/train/get_global_step.md): Get the global step tensor.

[`get_or_create_global_step(...)`](../tf/train/get_or_create_global_step.md): Returns and create (if necessary) the global step tensor.

[`global_step(...)`](../tf/train/global_step.md): Small helper to get the global step.

[`import_meta_graph(...)`](../tf/train/import_meta_graph.md): Recreates a Graph saved in a `MetaGraphDef` proto.

[`init_from_checkpoint(...)`](../tf/train/init_from_checkpoint.md): Initializes current variables with tensors loaded from given checkpoint.

[`input_producer(...)`](../tf/train/input_producer.md): Output the rows of `input_tensor` to a queue for an input pipeline. (deprecated)

[`inverse_time_decay(...)`](../tf/train/inverse_time_decay.md): Applies inverse time decay to the initial learning rate.

[`latest_checkpoint(...)`](../tf/train/latest_checkpoint.md): Finds the filename of latest saved checkpoint file.

[`limit_epochs(...)`](../tf/train/limit_epochs.md): Returns tensor `num_epochs` times and then raises an `OutOfRange` error. (deprecated)

[`linear_cosine_decay(...)`](../tf/train/linear_cosine_decay.md): Applies linear cosine decay to the learning rate.

[`list_variables(...)`](../tf/train/list_variables.md): Returns list of all variables in the checkpoint.

[`load_checkpoint(...)`](../tf/train/load_checkpoint.md): Returns `CheckpointReader` for checkpoint found in `ckpt_dir_or_file`.

[`load_variable(...)`](../tf/train/load_variable.md): Returns the tensor value of the given variable in the checkpoint.

[`match_filenames_once(...)`](../tf/io/match_filenames_once.md): Save the list of files matching pattern, so it is only computed once.

[`maybe_batch(...)`](../tf/train/maybe_batch.md): Conditionally creates batches of tensors based on `keep_input`. (deprecated)

[`maybe_batch_join(...)`](../tf/train/maybe_batch_join.md): Runs a list of tensors to conditionally fill a queue to create batches. (deprecated)

[`maybe_shuffle_batch(...)`](../tf/train/maybe_shuffle_batch.md): Creates batches by randomly shuffling conditionally-enqueued tensors. (deprecated)

[`maybe_shuffle_batch_join(...)`](../tf/train/maybe_shuffle_batch_join.md): Create batches by randomly shuffling conditionally-enqueued tensors. (deprecated)

[`natural_exp_decay(...)`](../tf/train/natural_exp_decay.md): Applies natural exponential decay to the initial learning rate.

[`noisy_linear_cosine_decay(...)`](../tf/train/noisy_linear_cosine_decay.md): Applies noisy linear cosine decay to the learning rate.

[`piecewise_constant(...)`](../tf/train/piecewise_constant.md): Piecewise constant from boundaries and interval values.

[`polynomial_decay(...)`](../tf/train/polynomial_decay.md): Applies a polynomial decay to the learning rate.

[`range_input_producer(...)`](../tf/train/range_input_producer.md): Produces the integers from 0 to limit-1 in a queue. (deprecated)

[`remove_checkpoint(...)`](../tf/train/remove_checkpoint.md): Removes a checkpoint given by `checkpoint_prefix`.

[`replica_device_setter(...)`](../tf/train/replica_device_setter.md): Return a `device function` to use when building a Graph for replicas.

[`sdca_fprint(...)`](../tf/train/sdca_fprint.md): Computes fingerprints of the input strings.

[`sdca_optimizer(...)`](../tf/train/sdca_optimizer.md): Distributed version of Stochastic Dual Coordinate Ascent (SDCA) optimizer for

[`sdca_shrink_l1(...)`](../tf/train/sdca_shrink_l1.md): Applies L1 regularization shrink step on the parameters.

[`shuffle_batch(...)`](../tf/train/shuffle_batch.md): Creates batches by randomly shuffling tensors. (deprecated)

[`shuffle_batch_join(...)`](../tf/train/shuffle_batch_join.md): Create batches by randomly shuffling tensors. (deprecated)

[`slice_input_producer(...)`](../tf/train/slice_input_producer.md): Produces a slice of each `Tensor` in `tensor_list`. (deprecated)

[`start_queue_runners(...)`](../tf/train/start_queue_runners.md): Starts all queue runners collected in the graph. (deprecated)

[`string_input_producer(...)`](../tf/train/string_input_producer.md): Output strings (e.g. filenames) to a queue for an input pipeline. (deprecated)

[`summary_iterator(...)`](../tf/train/summary_iterator.md): An iterator for reading `Event` protocol buffers from an event file.

[`update_checkpoint_state(...)`](../tf/train/update_checkpoint_state.md): Updates the content of the 'checkpoint' file.

[`warm_start(...)`](../tf/train/warm_start.md): Warm-starts a model using the given settings.

[`write_graph(...)`](../tf/io/write_graph.md): Writes a graph proto to a file.

