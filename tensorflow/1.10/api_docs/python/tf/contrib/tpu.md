<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.tpu" />
</div>

# Module: tf.contrib.tpu



Defined in [`tensorflow/contrib/tpu/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/tpu/__init__.py).

Ops related to Tensor Processing Units.










## Modules

[`profiler`](../../tf/contrib/tpu/profiler.md) module: Classes for TPU trace events.

## Classes

[`class CrossShardOptimizer`](../../tf/contrib/tpu/CrossShardOptimizer.md): An optimizer that averages gradients across TPU shards.

[`class DeviceAssignment`](../../tf/contrib/tpu/DeviceAssignment.md): Mapping from logical cores in a computation to the physical TPU topology.

[`class InfeedQueue`](../../tf/contrib/tpu/InfeedQueue.md): A helper object to build a device infeed queue.

[`class InputPipelineConfig`](../../tf/contrib/tpu/InputPipelineConfig.md): Please see the definition of these values in TPUConfig.

[`class RunConfig`](../../tf/contrib/tpu/RunConfig.md): RunConfig with TPU support.

[`class TPUConfig`](../../tf/contrib/tpu/TPUConfig.md): TPU related configuration required by `TPUEstimator`.

[`class TPUEstimator`](../../tf/contrib/tpu/TPUEstimator.md): Estimator with TPU support.

[`class TPUEstimatorSpec`](../../tf/contrib/tpu/TPUEstimatorSpec.md): Ops and objects returned from a `model_fn` and passed to `TPUEstimator`.

[`class Topology`](../../tf/contrib/tpu/Topology.md): Describes a set of TPU devices.

## Functions

[`TPUDistributionStrategy(...)`](../../tf/contrib/tpu/TPUDistributionStrategy.md)

[`batch_parallel(...)`](../../tf/contrib/tpu/batch_parallel.md): Shards `computation` along the batch dimension for parallel execution.

[`bfloat16_scope(...)`](../../tf/contrib/tpu/bfloat16_scope.md): Scope class for bfloat16 variables so that the model uses custom getter.

[`core(...)`](../../tf/contrib/tpu/core.md): Returns the device name for a core in a replicated TPU computation.

[`cross_replica_sum(...)`](../../tf/contrib/tpu/cross_replica_sum.md): An Op to sum inputs across replicated TPU instances. Each

[`device_assignment(...)`](../../tf/contrib/tpu/device_assignment.md): Computes a device_assignment of a computation across a TPU topology.

[`infeed_dequeue(...)`](../../tf/contrib/tpu/infeed_dequeue.md): A placeholder op for a value that will be fed into the computation.

[`infeed_dequeue_tuple(...)`](../../tf/contrib/tpu/infeed_dequeue_tuple.md): A placeholder op for values fed into the TPU simultaneously as a tuple.

[`initialize_system(...)`](../../tf/contrib/tpu/initialize_system.md): Initializes a distributed TPU system for use with TensorFlow.

[`keras_to_tpu_model(...)`](../../tf/contrib/tpu/keras_to_tpu_model.md): Copy `model` along with weights to the TPU.  Returns a TPU model. (experimental)

[`outfeed_enqueue(...)`](../../tf/contrib/tpu/outfeed_enqueue.md): An op which emits a single Tensor value from an XLA computation.

[`outfeed_enqueue_tuple(...)`](../../tf/contrib/tpu/outfeed_enqueue_tuple.md): An op which emits multiple Tensor values from an XLA computation.

[`repeat(...)`](../../tf/contrib/tpu/repeat.md): Builds a training loop that executes a fixed number of iterations.

[`replicate(...)`](../../tf/contrib/tpu/replicate.md): Builds a graph operator that runs a replicated TPU computation.

[`rewrite(...)`](../../tf/contrib/tpu/rewrite.md): Rewrites `computation` for execution on a TPU system.

[`shard(...)`](../../tf/contrib/tpu/shard.md): Shards `computation` for parallel execution.

[`shutdown_system(...)`](../../tf/contrib/tpu/shutdown_system.md): Shuts down a running a distributed TPU system.

[`while_loop(...)`](../../tf/contrib/tpu/while_loop.md): Builds a training loop for TPUs.

