<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.fisher_factors" />
</div>

# Module: tf.contrib.kfac.fisher_factors



Defined in [`tensorflow/contrib/kfac/python/ops/fisher_factors_lib.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/fisher_factors_lib.py).

FisherFactor definitions.

## Classes

[`class ConvDiagonalFactor`](../../../tf/contrib/kfac/fisher_factors/ConvDiagonalFactor.md): FisherFactor for a diagonal approx of a convolutional layer's Fisher.

[`class ConvInputKroneckerFactor`](../../../tf/contrib/kfac/fisher_factors/ConvInputKroneckerFactor.md): Kronecker factor for the input side of a convolutional layer.

[`class ConvOutputKroneckerFactor`](../../../tf/contrib/kfac/fisher_factors/ConvOutputKroneckerFactor.md): Kronecker factor for the output side of a convolutional layer.

[`class DiagonalFactor`](../../../tf/contrib/kfac/fisher_factors/DiagonalFactor.md): A base class for FisherFactors that use diagonal approximations.

[`class EmbeddingInputKroneckerFactor`](../../../tf/contrib/kfac/fisher_factors/EmbeddingInputKroneckerFactor.md): FisherFactor for input to an embedding layer.

[`class FisherFactor`](../../../tf/contrib/kfac/fisher_factors/FisherFactor.md): Base class for objects modeling factors of approximate Fisher blocks.

[`class FullFactor`](../../../tf/contrib/kfac/fisher_factors/FullFactor.md): FisherFactor for a full matrix representation of the Fisher of a parameter.

[`class FullyConnectedDiagonalFactor`](../../../tf/contrib/kfac/fisher_factors/FullyConnectedDiagonalFactor.md): FisherFactor for a diagonal approx of a fully-connected layer's Fisher.

[`class FullyConnectedKroneckerFactor`](../../../tf/contrib/kfac/fisher_factors/FullyConnectedKroneckerFactor.md): Kronecker factor for the input or output side of a fully-connected layer.

[`class NaiveDiagonalFactor`](../../../tf/contrib/kfac/fisher_factors/NaiveDiagonalFactor.md): FisherFactor for a diagonal approximation of any type of param's Fisher.

## Functions

[`append_homog(...)`](../../../tf/contrib/kfac/fisher_factors/append_homog.md): Appends a homogeneous coordinate to the last dimension of a Tensor.

[`compute_cov(...)`](../../../tf/contrib/kfac/fisher_factors/compute_cov.md): Compute the empirical second moment of the rows of a 2D Tensor.

[`covariance_initializer(...)`](../../../tf/contrib/kfac/fisher_factors/covariance_initializer.md)

[`diagonal_covariance_initializer(...)`](../../../tf/contrib/kfac/fisher_factors/diagonal_covariance_initializer.md)

[`inverse_initializer(...)`](../../../tf/contrib/kfac/fisher_factors/inverse_initializer.md)

[`scalar_or_tensor_to_string(...)`](../../../tf/contrib/kfac/fisher_factors/scalar_or_tensor_to_string.md)

[`scope_string_from_name(...)`](../../../tf/contrib/kfac/fisher_factors/scope_string_from_name.md)

[`scope_string_from_params(...)`](../../../tf/contrib/kfac/fisher_factors/scope_string_from_params.md): Builds a variable scope string name from the given parameters.

[`set_global_constants(...)`](../../../tf/contrib/kfac/fisher_factors/set_global_constants.md): Sets various global constants used by the classes in this module.

