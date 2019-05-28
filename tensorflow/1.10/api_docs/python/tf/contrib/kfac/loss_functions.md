<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.loss_functions" />
</div>

# Module: tf.contrib.kfac.loss_functions



Defined in [`tensorflow/contrib/kfac/python/ops/loss_functions_lib.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/loss_functions_lib.py).

Loss functions to be used by LayerCollection.

## Classes

[`class CategoricalLogitsNegativeLogProbLoss`](../../../tf/contrib/kfac/loss_functions/CategoricalLogitsNegativeLogProbLoss.md): Neg log prob loss for a categorical distribution parameterized by logits.

[`class DistributionNegativeLogProbLoss`](../../../tf/contrib/kfac/loss_functions/DistributionNegativeLogProbLoss.md): Base class for neg log prob losses that use the TF Distribution classes.

[`class LossFunction`](../../../tf/contrib/kfac/loss_functions/LossFunction.md): Abstract base class for loss functions.

[`class MultiBernoulliNegativeLogProbLoss`](../../../tf/contrib/kfac/loss_functions/MultiBernoulliNegativeLogProbLoss.md): Neg log prob loss for multiple Bernoulli distributions param'd by logits.

[`class NaturalParamsNegativeLogProbLoss`](../../../tf/contrib/kfac/loss_functions/NaturalParamsNegativeLogProbLoss.md): Base class for neg log prob losses whose inputs are 'natural' parameters.

[`class NegativeLogProbLoss`](../../../tf/contrib/kfac/loss_functions/NegativeLogProbLoss.md): Abstract base class for loss functions that are negative log probs.

[`class NormalMeanNegativeLogProbLoss`](../../../tf/contrib/kfac/loss_functions/NormalMeanNegativeLogProbLoss.md): Neg log prob loss for a normal distribution parameterized by a mean vector.

[`class NormalMeanVarianceNegativeLogProbLoss`](../../../tf/contrib/kfac/loss_functions/NormalMeanVarianceNegativeLogProbLoss.md): Negative log prob loss for a normal distribution with mean and variance.

[`class OnehotCategoricalLogitsNegativeLogProbLoss`](../../../tf/contrib/kfac/loss_functions/OnehotCategoricalLogitsNegativeLogProbLoss.md): Neg log prob loss for a categorical distribution with onehot targets.

## Functions

[`insert_slice_in_zeros(...)`](../../../tf/contrib/kfac/loss_functions/insert_slice_in_zeros.md): Inserts slice into a larger tensor of zeros.

