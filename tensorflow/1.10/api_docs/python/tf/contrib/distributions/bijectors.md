<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distributions.bijectors" />
</div>

# Module: tf.contrib.distributions.bijectors



Defined in [`tensorflow/contrib/distributions/python/ops/bijectors/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/distributions/python/ops/bijectors/__init__.py).

Bijector Ops.



## Classes

[`class AbsoluteValue`](../../../tf/contrib/distributions/bijectors/AbsoluteValue.md): Computes `Y = g(X) = Abs(X)`, element-wise.

[`class Affine`](../../../tf/contrib/distributions/bijectors/Affine.md): Compute `Y = g(X; shift, scale) = scale @ X + shift`.

[`class AffineLinearOperator`](../../../tf/contrib/distributions/bijectors/AffineLinearOperator.md): Compute `Y = g(X; shift, scale) = scale @ X + shift`.

[`class AffineScalar`](../../../tf/contrib/distributions/bijectors/AffineScalar.md): Compute `Y = g(X; shift, scale) = scale * X + shift`.

[`class BatchNormalization`](../../../tf/contrib/distributions/bijectors/BatchNormalization.md): Compute `Y = g(X) s.t. X = g^-1(Y) = (Y - mean(Y)) / std(Y)`.

[`class Bijector`](../../../tf/contrib/distributions/bijectors/Bijector.md): Interface for transformations of a `Distribution` sample.

[`class Chain`](../../../tf/contrib/distributions/bijectors/Chain.md): Bijector which applies a sequence of bijectors.

[`class CholeskyOuterProduct`](../../../tf/contrib/distributions/bijectors/CholeskyOuterProduct.md): Compute `g(X) = X @ X.T`; X is lower-triangular, positive-diagonal matrix.

[`class ConditionalBijector`](../../../tf/contrib/distributions/bijectors/ConditionalBijector.md): Conditional Bijector is a Bijector that allows intrinsic conditioning.

[`class Exp`](../../../tf/contrib/distributions/bijectors/Exp.md): Compute `Y = g(X) = exp(X)`.

[`class FillTriangular`](../../../tf/contrib/distributions/bijectors/FillTriangular.md): Transforms vectors to triangular.

[`class Gumbel`](../../../tf/contrib/distributions/bijectors/Gumbel.md): Compute `Y = g(X) = exp(-exp(-(X - loc) / scale))`.

[`class Identity`](../../../tf/contrib/distributions/bijectors/Identity.md): Compute Y = g(X) = X.

[`class Inline`](../../../tf/contrib/distributions/bijectors/Inline.md): Bijector constructed from custom callables.

[`class Invert`](../../../tf/contrib/distributions/bijectors/Invert.md): Bijector which inverts another Bijector.

[`class Kumaraswamy`](../../../tf/contrib/distributions/bijectors/Kumaraswamy.md): Compute `Y = g(X) = (1 - (1 - X)**(1 / b))**(1 / a), X in [0, 1]`.

[`class MaskedAutoregressiveFlow`](../../../tf/contrib/distributions/bijectors/MaskedAutoregressiveFlow.md): Affine MaskedAutoregressiveFlow bijector for vector-valued events.

[`class MatrixInverseTriL`](../../../tf/contrib/distributions/bijectors/MatrixInverseTriL.md): Computes `g(L) = inv(L)`, where `L` is a lower-triangular matrix.

[`class Ordered`](../../../tf/contrib/distributions/bijectors/Ordered.md): Bijector which maps a tensor x_k that has increasing elements in the last

[`class Permute`](../../../tf/contrib/distributions/bijectors/Permute.md): Permutes the rightmost dimension of a `Tensor`.

[`class PowerTransform`](../../../tf/contrib/distributions/bijectors/PowerTransform.md): Compute `Y = g(X) = (1 + X * c)**(1 / c), X >= -1 / c`.

[`class RealNVP`](../../../tf/contrib/distributions/bijectors/RealNVP.md): RealNVP "affine coupling layer" for vector-valued events.

[`class Reshape`](../../../tf/contrib/distributions/bijectors/Reshape.md): Reshapes the `event_shape` of a `Tensor`.

[`class ScaleTriL`](../../../tf/contrib/distributions/bijectors/ScaleTriL.md): Transforms unconstrained vectors to TriL matrices with positive diagonal.

[`class Sigmoid`](../../../tf/contrib/distributions/bijectors/Sigmoid.md): Bijector which computes `Y = g(X) = 1 / (1 + exp(-X))`.

[`class SinhArcsinh`](../../../tf/contrib/distributions/bijectors/SinhArcsinh.md): Compute `Y = g(X) = Sinh( (Arcsinh(X) + skewness) * tailweight )`.

[`class SoftmaxCentered`](../../../tf/contrib/distributions/bijectors/SoftmaxCentered.md): Bijector which computes `Y = g(X) = exp([X 0]) / sum(exp([X 0]))`.

[`class Softplus`](../../../tf/contrib/distributions/bijectors/Softplus.md): Bijector which computes `Y = g(X) = Log[1 + exp(X)]`.

[`class Softsign`](../../../tf/contrib/distributions/bijectors/Softsign.md): Bijector which computes `Y = g(X) = X / (1 + |X|)`.

[`class Square`](../../../tf/contrib/distributions/bijectors/Square.md): Compute `g(X) = X^2`; X is a positive real number.

[`class TransformDiagonal`](../../../tf/contrib/distributions/bijectors/TransformDiagonal.md): Applies a Bijector to the diagonal of a matrix.

## Functions

[`masked_autoregressive_default_template(...)`](../../../tf/contrib/distributions/bijectors/masked_autoregressive_default_template.md): Build the Masked Autoregressive Density Estimator (Germain et al., 2015). (deprecated)

[`masked_dense(...)`](../../../tf/contrib/distributions/bijectors/masked_dense.md): A autoregressively masked dense layer. Analogous to <a href="../../../tf/layers/dense.md"><code>tf.layers.dense</code></a>. (deprecated)

[`real_nvp_default_template(...)`](../../../tf/contrib/distributions/bijectors/real_nvp_default_template.md): Build a scale-and-shift function using a multi-layer neural network. (deprecated)

