<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.fisher_blocks" />
</div>

# Module: tf.contrib.kfac.fisher_blocks



Defined in [`tensorflow/contrib/kfac/python/ops/fisher_blocks_lib.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/fisher_blocks_lib.py).

FisherBlock definitions.

## Classes

[`class ConvDiagonalFB`](../../../tf/contrib/kfac/fisher_blocks/ConvDiagonalFB.md): FisherBlock for 2-D convolutional layers using a diagonal approx.

[`class ConvKFCBasicFB`](../../../tf/contrib/kfac/fisher_blocks/ConvKFCBasicFB.md): FisherBlock for convolutional layers using the basic KFC approx.

[`class EmbeddingKFACFB`](../../../tf/contrib/kfac/fisher_blocks/EmbeddingKFACFB.md): K-FAC FisherBlock for embedding layers.

[`class FisherBlock`](../../../tf/contrib/kfac/fisher_blocks/FisherBlock.md): Abstract base class for objects modeling approximate Fisher matrix blocks.

[`class FullFB`](../../../tf/contrib/kfac/fisher_blocks/FullFB.md): FisherBlock using a full matrix estimate (no approximations).

[`class FullyConnectedDiagonalFB`](../../../tf/contrib/kfac/fisher_blocks/FullyConnectedDiagonalFB.md): FisherBlock for fully-connected (dense) layers using a diagonal approx.

[`class FullyConnectedKFACBasicFB`](../../../tf/contrib/kfac/fisher_blocks/FullyConnectedKFACBasicFB.md): K-FAC FisherBlock for fully-connected (dense) layers.

[`class KroneckerProductFB`](../../../tf/contrib/kfac/fisher_blocks/KroneckerProductFB.md): A base class for blocks with separate input and output Kronecker factors.

[`class NaiveDiagonalFB`](../../../tf/contrib/kfac/fisher_blocks/NaiveDiagonalFB.md): FisherBlock using a diagonal matrix approximation.

## Functions

[`compute_pi_adjusted_damping(...)`](../../../tf/contrib/kfac/fisher_blocks/compute_pi_adjusted_damping.md)

[`compute_pi_tracenorm(...)`](../../../tf/contrib/kfac/fisher_blocks/compute_pi_tracenorm.md): Computes the scalar constant pi for Tikhonov regularization/damping.

[`normalize_damping(...)`](../../../tf/contrib/kfac/fisher_blocks/normalize_damping.md): Normalize damping after adjusting scale by NORMALIZE_DAMPING_POWER.

[`num_conv_locations(...)`](../../../tf/contrib/kfac/fisher_blocks/num_conv_locations.md): Returns the number of spatial locations a 2D Conv kernel is applied to.

[`set_global_constants(...)`](../../../tf/contrib/kfac/fisher_blocks/set_global_constants.md): Sets various global constants used by the classes in this module.

