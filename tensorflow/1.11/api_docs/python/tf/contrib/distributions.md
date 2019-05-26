<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distributions" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="FULLY_REPARAMETERIZED"/>
<meta itemprop="property" content="NOT_REPARAMETERIZED"/>
</div>

# Module: tf.contrib.distributions



Defined in [`tensorflow/contrib/distributions/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/distributions/__init__.py).

Classes representing statistical distributions and ops for working with them.

## Modules

[`bijectors`](../../tf/contrib/distributions/bijectors.md) module: Bijector Ops.

## Classes

[`class Autoregressive`](../../tf/contrib/distributions/Autoregressive.md): Autoregressive distributions.

[`class BatchReshape`](../../tf/contrib/distributions/BatchReshape.md): The Batch-Reshaping distribution.

[`class Bernoulli`](../../tf/distributions/Bernoulli.md): Bernoulli distribution.

[`class Beta`](../../tf/distributions/Beta.md): Beta distribution.

[`class BetaWithSoftplusConcentration`](../../tf/contrib/distributions/BetaWithSoftplusConcentration.md): Beta with softplus transform of `concentration1` and `concentration0`.

[`class Binomial`](../../tf/contrib/distributions/Binomial.md): Binomial distribution.

[`class Categorical`](../../tf/distributions/Categorical.md): Categorical distribution.

[`class Cauchy`](../../tf/contrib/distributions/Cauchy.md): The Cauchy distribution with location `loc` and scale `scale`.

[`class Chi2`](../../tf/contrib/distributions/Chi2.md): Chi2 distribution.

[`class Chi2WithAbsDf`](../../tf/contrib/distributions/Chi2WithAbsDf.md): Chi2 with parameter transform `df = floor(abs(df))`.

[`class ConditionalDistribution`](../../tf/contrib/distributions/ConditionalDistribution.md): Distribution that supports intrinsic parameters (local latents).

[`class ConditionalTransformedDistribution`](../../tf/contrib/distributions/ConditionalTransformedDistribution.md): A TransformedDistribution that allows intrinsic conditioning.

[`class Deterministic`](../../tf/contrib/distributions/Deterministic.md): Scalar `Deterministic` distribution on the real line.

[`class Dirichlet`](../../tf/distributions/Dirichlet.md): Dirichlet distribution.

[`class DirichletMultinomial`](../../tf/distributions/DirichletMultinomial.md): Dirichlet-Multinomial compound distribution.

[`class Distribution`](../../tf/distributions/Distribution.md): A generic probability distribution base class.

[`class ExpRelaxedOneHotCategorical`](../../tf/contrib/distributions/ExpRelaxedOneHotCategorical.md): ExpRelaxedOneHotCategorical distribution with temperature and logits.

[`class Exponential`](../../tf/distributions/Exponential.md): Exponential distribution.

[`class ExponentialWithSoftplusRate`](../../tf/contrib/distributions/ExponentialWithSoftplusRate.md): Exponential with softplus transform on `rate`.

[`class Gamma`](../../tf/distributions/Gamma.md): Gamma distribution.

[`class GammaWithSoftplusConcentrationRate`](../../tf/contrib/distributions/GammaWithSoftplusConcentrationRate.md): `Gamma` with softplus of `concentration` and `rate`.

[`class Geometric`](../../tf/contrib/distributions/Geometric.md): Geometric distribution.

[`class HalfNormal`](../../tf/contrib/distributions/HalfNormal.md): The Half Normal distribution with scale `scale`.

[`class Independent`](../../tf/contrib/distributions/Independent.md): Independent distribution from batch of distributions.

[`class InverseGamma`](../../tf/contrib/distributions/InverseGamma.md): InverseGamma distribution.

[`class InverseGammaWithSoftplusConcentrationRate`](../../tf/contrib/distributions/InverseGammaWithSoftplusConcentrationRate.md): `InverseGamma` with softplus of `concentration` and `rate`.

[`class Kumaraswamy`](../../tf/contrib/distributions/Kumaraswamy.md): Kumaraswamy distribution.

[`class Laplace`](../../tf/distributions/Laplace.md): The Laplace distribution with location `loc` and `scale` parameters.

[`class LaplaceWithSoftplusScale`](../../tf/contrib/distributions/LaplaceWithSoftplusScale.md): Laplace with softplus applied to `scale`.

[`class Logistic`](../../tf/contrib/distributions/Logistic.md): The Logistic distribution with location `loc` and `scale` parameters.

[`class Mixture`](../../tf/contrib/distributions/Mixture.md): Mixture distribution.

[`class MixtureSameFamily`](../../tf/contrib/distributions/MixtureSameFamily.md): Mixture (same-family) distribution.

[`class Multinomial`](../../tf/distributions/Multinomial.md): Multinomial distribution.

[`class MultivariateNormalDiag`](../../tf/contrib/distributions/MultivariateNormalDiag.md): The multivariate normal distribution on `R^k`.

[`class MultivariateNormalDiagPlusLowRank`](../../tf/contrib/distributions/MultivariateNormalDiagPlusLowRank.md): The multivariate normal distribution on `R^k`.

[`class MultivariateNormalDiagWithSoftplusScale`](../../tf/contrib/distributions/MultivariateNormalDiagWithSoftplusScale.md): MultivariateNormalDiag with `diag_stddev = softplus(diag_stddev)`.

[`class MultivariateNormalFullCovariance`](../../tf/contrib/distributions/MultivariateNormalFullCovariance.md): The multivariate normal distribution on `R^k`.

[`class MultivariateNormalTriL`](../../tf/contrib/distributions/MultivariateNormalTriL.md): The multivariate normal distribution on `R^k`.

[`class NegativeBinomial`](../../tf/contrib/distributions/NegativeBinomial.md): NegativeBinomial distribution.

[`class Normal`](../../tf/distributions/Normal.md): The Normal distribution with location `loc` and `scale` parameters.

[`class NormalWithSoftplusScale`](../../tf/contrib/distributions/NormalWithSoftplusScale.md): Normal with softplus applied to `scale`.

[`class OneHotCategorical`](../../tf/contrib/distributions/OneHotCategorical.md): OneHotCategorical distribution.

[`class Poisson`](../../tf/contrib/distributions/Poisson.md): Poisson distribution.

[`class PoissonLogNormalQuadratureCompound`](../../tf/contrib/distributions/PoissonLogNormalQuadratureCompound.md): `PoissonLogNormalQuadratureCompound` distribution.

[`class QuantizedDistribution`](../../tf/contrib/distributions/QuantizedDistribution.md): Distribution representing the quantization `Y = ceiling(X)`.

[`class RegisterKL`](../../tf/distributions/RegisterKL.md): Decorator to register a KL divergence implementation function.

[`class RelaxedBernoulli`](../../tf/contrib/distributions/RelaxedBernoulli.md): RelaxedBernoulli distribution with temperature and logits parameters.

[`class RelaxedOneHotCategorical`](../../tf/contrib/distributions/RelaxedOneHotCategorical.md): RelaxedOneHotCategorical distribution with temperature and logits.

[`class ReparameterizationType`](../../tf/distributions/ReparameterizationType.md): Instances of this class represent how sampling is reparameterized.

[`class SeedStream`](../../tf/contrib/distributions/SeedStream.md): Local PRNG for amplifying seed entropy into seeds for base operations.

[`class SinhArcsinh`](../../tf/contrib/distributions/SinhArcsinh.md): The SinhArcsinh transformation of a distribution on `(-inf, inf)`.

[`class StudentT`](../../tf/distributions/StudentT.md): Student's t-distribution.

[`class StudentTWithAbsDfSoftplusScale`](../../tf/contrib/distributions/StudentTWithAbsDfSoftplusScale.md): StudentT with `df = floor(abs(df))` and `scale = softplus(scale)`.

[`class TransformedDistribution`](../../tf/contrib/distributions/TransformedDistribution.md): A Transformed Distribution.

[`class Uniform`](../../tf/distributions/Uniform.md): Uniform distribution with `low` and `high` parameters.

[`class VectorDeterministic`](../../tf/contrib/distributions/VectorDeterministic.md): Vector `Deterministic` distribution on `R^k`.

[`class VectorDiffeomixture`](../../tf/contrib/distributions/VectorDiffeomixture.md): VectorDiffeomixture distribution.

[`class VectorExponentialDiag`](../../tf/contrib/distributions/VectorExponentialDiag.md): The vectorization of the Exponential distribution on `R^k`.

[`class VectorLaplaceDiag`](../../tf/contrib/distributions/VectorLaplaceDiag.md): The vectorization of the Laplace distribution on `R^k`.

[`class VectorSinhArcsinhDiag`](../../tf/contrib/distributions/VectorSinhArcsinhDiag.md): The (diagonal) SinhArcsinh transformation of a distribution on `R^k`.

[`class WishartCholesky`](../../tf/contrib/distributions/WishartCholesky.md): The matrix Wishart distribution on positive definite matrices.

[`class WishartFull`](../../tf/contrib/distributions/WishartFull.md): The matrix Wishart distribution on positive definite matrices.

## Functions

[`assign_log_moving_mean_exp(...)`](../../tf/contrib/distributions/assign_log_moving_mean_exp.md): Compute the log of the exponentially weighted moving mean of the exp.

[`assign_moving_mean_variance(...)`](../../tf/contrib/distributions/assign_moving_mean_variance.md): Compute exponentially weighted moving {mean,variance} of a streaming value.

[`auto_correlation(...)`](../../tf/contrib/distributions/auto_correlation.md): Auto correlation along one axis.

[`estimator_head_distribution_regression(...)`](../../tf/contrib/distributions/estimator_head_distribution_regression.md): Creates a `Head` for regression under a generic distribution. (deprecated)

[`fill_triangular(...)`](../../tf/contrib/distributions/fill_triangular.md): Creates a (batch of) triangular matrix from a vector of inputs.

[`fill_triangular_inverse(...)`](../../tf/contrib/distributions/fill_triangular_inverse.md): Creates a vector from a (batch of) triangular matrix.

[`kl_divergence(...)`](../../tf/distributions/kl_divergence.md): Get the KL-divergence KL(distribution_a || distribution_b).

[`matrix_diag_transform(...)`](../../tf/contrib/distributions/matrix_diag_transform.md): Transform diagonal of [batch-]matrix, leave rest of matrix unchanged.

[`moving_mean_variance(...)`](../../tf/contrib/distributions/moving_mean_variance.md): Compute exponentially weighted moving {mean,variance} of a streaming value.

[`normal_conjugates_known_scale_posterior(...)`](../../tf/contrib/distributions/normal_conjugates_known_scale_posterior.md): Posterior Normal distribution with conjugate prior on the mean.

[`normal_conjugates_known_scale_predictive(...)`](../../tf/contrib/distributions/normal_conjugates_known_scale_predictive.md): Posterior predictive Normal distribution w. conjugate prior on the mean.

[`percentile(...)`](../../tf/contrib/distributions/percentile.md): Compute the `q`-th percentile of `x`.

[`quadrature_scheme_lognormal_gauss_hermite(...)`](../../tf/contrib/distributions/quadrature_scheme_lognormal_gauss_hermite.md): Use Gauss-Hermite quadrature to form quadrature on positive-reals. (deprecated)

[`quadrature_scheme_lognormal_quantiles(...)`](../../tf/contrib/distributions/quadrature_scheme_lognormal_quantiles.md): Use LogNormal quantiles to form quadrature on positive-reals. (deprecated)

[`quadrature_scheme_softmaxnormal_gauss_hermite(...)`](../../tf/contrib/distributions/quadrature_scheme_softmaxnormal_gauss_hermite.md): Use Gauss-Hermite quadrature to form quadrature on `K - 1` simplex. (deprecated)

[`quadrature_scheme_softmaxnormal_quantiles(...)`](../../tf/contrib/distributions/quadrature_scheme_softmaxnormal_quantiles.md): Use SoftmaxNormal quantiles to form quadrature on `K - 1` simplex. (deprecated)

[`reduce_weighted_logsumexp(...)`](../../tf/contrib/distributions/reduce_weighted_logsumexp.md): Computes `log(abs(sum(weight * exp(elements across tensor dimensions))))`.

[`softplus_inverse(...)`](../../tf/contrib/distributions/softplus_inverse.md): Computes the inverse softplus, i.e., x = softplus_inverse(softplus(x)).

[`tridiag(...)`](../../tf/contrib/distributions/tridiag.md): Creates a matrix with values set above, below, and on the diagonal.

## Other Members

`FULLY_REPARAMETERIZED`

`NOT_REPARAMETERIZED`

