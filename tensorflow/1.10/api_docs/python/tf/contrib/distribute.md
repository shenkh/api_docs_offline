<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distribute" />
</div>

# Module: tf.contrib.distribute



Defined in [`tensorflow/contrib/distribute/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/distribute/__init__.py).

Prototype of a distributed computation library for TF.

## Classes

[`class AllReduceCrossTowerOps`](../../tf/contrib/distribute/AllReduceCrossTowerOps.md): Reduction using all reduce.

[`class CrossTowerOps`](../../tf/contrib/distribute/CrossTowerOps.md): Base class for cross-tower reduction and broadcasting algorithms.

[`class DistributionStrategy`](../../tf/contrib/distribute/DistributionStrategy.md): A list of devices with a state & compute distribution policy.

[`class MirroredStrategy`](../../tf/contrib/distribute/MirroredStrategy.md): Mirrors vars to distribute across multiple devices on a single machine.

[`class Monitor`](../../tf/contrib/distribute/Monitor.md): Executes training steps, recovers and checkpoints.

[`class OneDeviceStrategy`](../../tf/contrib/distribute/OneDeviceStrategy.md): A distribution strategy for running on a single device.

[`class ReductionToOneDeviceCrossTowerOps`](../../tf/contrib/distribute/ReductionToOneDeviceCrossTowerOps.md): Always do reduction to one device first and then do broadcasting.

[`class StandardInputStep`](../../tf/contrib/distribute/StandardInputStep.md): Step with a standard implementation of input handling.

[`class StandardSingleLossStep`](../../tf/contrib/distribute/StandardSingleLossStep.md): A step function that implements a training step for a feed forward network.

[`class Step`](../../tf/contrib/distribute/Step.md): Interface for performing each step of a training algorithm.

[`class TPUStrategy`](../../tf/contrib/distribute/TPUStrategy.md): Experimental TPU distribution strategy implementation.

[`class TowerContext`](../../tf/contrib/distribute/TowerContext.md): DistributionStrategy API inside a `call_for_each_tower()` call.

## Functions

[`get_cross_tower_context(...)`](../../tf/contrib/distribute/get_cross_tower_context.md): Returns the current DistributionStrategy if in a cross-tower context.

[`get_distribution_strategy(...)`](../../tf/contrib/distribute/get_distribution_strategy.md): Returns the current `DistributionStrategy` object.

[`get_loss_reduction(...)`](../../tf/contrib/distribute/get_loss_reduction.md): Reduce `aggregation` corresponding to the last loss reduction.

[`get_tower_context(...)`](../../tf/contrib/distribute/get_tower_context.md): Returns the current TowerContext or None if in a cross-tower context.

[`has_distribution_strategy(...)`](../../tf/contrib/distribute/has_distribution_strategy.md): Return if there is a current non-default `DistributionStrategy`.

[`require_tower_context(...)`](../../tf/contrib/distribute/require_tower_context.md): Verify in `tower_ctx` tower context.

