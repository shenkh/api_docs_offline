<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distribute" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.contrib.distribute



Defined in [`tensorflow/contrib/distribute/__init__.py`](/code/stable/tensorflow/contrib/distribute/__init__.py).

A distributed computation library for TF.

See [tensorflow/contrib/distribute/README.md](
https://www.tensorflow.org/code/tensorflow/contrib/distribute/README.md)
for overview and examples.

## Classes

[`class AllReduceCrossTowerOps`](../../tf/contrib/distribute/AllReduceCrossTowerOps.md): Reduction using all reduce.

[`class CollectiveAllReduceStrategy`](../../tf/contrib/distribute/CollectiveAllReduceStrategy.md): Distribution strategy that uses collective ops for all-reduce.

[`class CrossTowerOps`](../../tf/contrib/distribute/CrossTowerOps.md): Base class for cross-tower reduction and broadcasting algorithms.

[`class DistributeConfig`](../../tf/contrib/distribute/DistributeConfig.md): A config tuple for distribution strategies.

[`class DistributionStrategy`](../../tf/contrib/distribute/DistributionStrategy.md): A list of devices with a state & compute distribution policy.

[`class MirroredStrategy`](../../tf/contrib/distribute/MirroredStrategy.md): Mirrors vars to distribute across multiple devices and machines.

[`class Monitor`](../../tf/contrib/distribute/Monitor.md): Executes training steps, recovers and checkpoints.

[`class OneDeviceStrategy`](../../tf/contrib/distribute/OneDeviceStrategy.md): A distribution strategy for running on a single device.

[`class ParameterServerStrategy`](../../tf/contrib/distribute/ParameterServerStrategy.md): A parameter server DistributionStrategy.

[`class ReductionToOneDeviceCrossTowerOps`](../../tf/contrib/distribute/ReductionToOneDeviceCrossTowerOps.md): Always do reduction to one device first and then do broadcasting.

[`class StandardInputStep`](../../tf/contrib/distribute/StandardInputStep.md): Step with a standard implementation of input handling.

[`class StandardSingleLossStep`](../../tf/contrib/distribute/StandardSingleLossStep.md): A step function that implements a training step for a feed forward network.

[`class Step`](../../tf/contrib/distribute/Step.md): Interface for performing each step of a training algorithm.

[`class TPUStrategy`](../../tf/contrib/distribute/TPUStrategy.md): Experimental TPU distribution strategy implementation.

[`class TowerContext`](../../tf/contrib/distribute/TowerContext.md): DistributionStrategy API inside a `call_for_each_tower()` call.

[`class UpdateContext`](../../tf/contrib/distribute/UpdateContext.md): Context manager when you are in `update()` or `update_non_slot()`.

## Functions

[`get_cross_tower_context(...)`](../../tf/contrib/distribute/get_cross_tower_context.md): Returns the current DistributionStrategy if in a cross-tower context.

[`get_distribution_strategy(...)`](../../tf/contrib/distribute/get_distribution_strategy.md): Returns the current `DistributionStrategy` object.

[`get_loss_reduction(...)`](../../tf/contrib/distribute/get_loss_reduction.md): Reduce `aggregation` corresponding to the last loss reduction.

[`get_tower_context(...)`](../../tf/contrib/distribute/get_tower_context.md): Returns the current TowerContext or None if in a cross-tower context.

[`has_distribution_strategy(...)`](../../tf/contrib/distribute/has_distribution_strategy.md): Return if there is a current non-default `DistributionStrategy`.

[`require_tower_context(...)`](../../tf/contrib/distribute/require_tower_context.md): Verify in `tower_ctx` tower context.

[`run_standard_tensorflow_server(...)`](../../tf/contrib/distribute/run_standard_tensorflow_server.md): Starts a standard TensorFlow server.

