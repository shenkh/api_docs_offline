<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.loss_functions.NormalMeanVarianceNegativeLogProbLoss" />
<meta itemprop="property" content="dist"/>
<meta itemprop="property" content="fisher_factor_inner_shape"/>
<meta itemprop="property" content="fisher_factor_inner_static_shape"/>
<meta itemprop="property" content="hessian_factor_inner_shape"/>
<meta itemprop="property" content="hessian_factor_inner_static_shape"/>
<meta itemprop="property" content="inputs"/>
<meta itemprop="property" content="params"/>
<meta itemprop="property" content="targets"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="evaluate"/>
<meta itemprop="property" content="evaluate_on_sample"/>
<meta itemprop="property" content="multiply_fisher"/>
<meta itemprop="property" content="multiply_fisher_factor"/>
<meta itemprop="property" content="multiply_fisher_factor_replicated_one_hot"/>
<meta itemprop="property" content="multiply_fisher_factor_transpose"/>
<meta itemprop="property" content="multiply_hessian"/>
<meta itemprop="property" content="multiply_hessian_factor"/>
<meta itemprop="property" content="multiply_hessian_factor_replicated_one_hot"/>
<meta itemprop="property" content="multiply_hessian_factor_transpose"/>
<meta itemprop="property" content="sample"/>
</div>

# tf.contrib.kfac.loss_functions.NormalMeanVarianceNegativeLogProbLoss

## Class `NormalMeanVarianceNegativeLogProbLoss`

Inherits From: [`DistributionNegativeLogProbLoss`](../../../../tf/contrib/kfac/loss_functions/DistributionNegativeLogProbLoss.md)



Defined in [`tensorflow/contrib/kfac/python/ops/loss_functions.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/loss_functions.py).

Negative log prob loss for a normal distribution with mean and variance.

This class parameterizes a multivariate normal distribution with n independent
dimensions. Unlike `NormalMeanNegativeLogProbLoss`, this class does not
assume the variance is held constant. The Fisher Information for n = 1
is given by,

F = [[1 / variance,                0],
     [           0, 0.5 / variance^2]]

where the parameters of the distribution are concatenated into a single
vector as [mean, variance]. For n > 1, the mean parameter vector is
concatenated with the variance parameter vector.

See https://www.ii.pwr.edu.pl/~tomczak/PDF/[JMT]Fisher_inf.pdf for derivation.

## Properties

<h3 id="dist"><code>dist</code></h3>

The underlying tf.distributions.Distribution.

<h3 id="fisher_factor_inner_shape"><code>fisher_factor_inner_shape</code></h3>

The shape of the tensor returned by multiply_fisher_factor.

<h3 id="fisher_factor_inner_static_shape"><code>fisher_factor_inner_static_shape</code></h3>

Static version of fisher_factor_inner_shape.

<h3 id="hessian_factor_inner_shape"><code>hessian_factor_inner_shape</code></h3>

The shape of the tensor returned by multiply_hessian_factor.

<h3 id="hessian_factor_inner_static_shape"><code>hessian_factor_inner_static_shape</code></h3>

Static version of hessian_factor_inner_shape.

<h3 id="inputs"><code>inputs</code></h3>

The inputs to the loss function (excluding the targets).

<h3 id="params"><code>params</code></h3>

Parameters to the underlying distribution.

<h3 id="targets"><code>targets</code></h3>

The targets being predicted by the model.

#### Returns:

None or Tensor of appropriate shape for calling self._evaluate() on.



## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    mean,
    variance,
    targets=None,
    seed=None
)
```

Initialize self.  See help(type(self)) for accurate signature.

<h3 id="evaluate"><code>evaluate</code></h3>

``` python
evaluate()
```

Evaluate the loss function on the targets.

<h3 id="evaluate_on_sample"><code>evaluate_on_sample</code></h3>

``` python
evaluate_on_sample(seed=None)
```

Evaluates the log probability on a random sample.

#### Args:

* <b>`seed`</b>: int or None. Random seed for this draw from the distribution.


#### Returns:

Log probability of sampled targets, summed across examples.

<h3 id="multiply_fisher"><code>multiply_fisher</code></h3>

``` python
multiply_fisher(vecs)
```

Right-multiply a vector by the Fisher.

#### Args:

* <b>`vector`</b>: The vector to multiply.  Must be the same shape(s) as the
    'inputs' property.


#### Returns:

The vector right-multiplied by the Fisher.  Will be of the same shape(s)
as the 'inputs' property.

<h3 id="multiply_fisher_factor"><code>multiply_fisher_factor</code></h3>

``` python
multiply_fisher_factor(vecs)
```

Right-multiply a vector by a factor B of the Fisher.

Here the 'Fisher' is the Fisher information matrix (i.e. expected outer-
product of gradients) with respect to the parameters of the underlying
probability distribtion (whose log-prob defines the loss). Typically this
will be block-diagonal across different cases in the batch, since the
distribution is usually (but not always) conditionally iid across different
cases.

Note that B can be any matrix satisfying B * B^T = F where F is the Fisher,
but will agree with the one used in the other methods of this class.

#### Args:

* <b>`vector`</b>: The vector to multiply.  Must be of the shape given by the
    'fisher_factor_inner_shape' property.


#### Returns:

The vector right-multiplied by B. Will be of the same shape(s) as the
'inputs' property.

<h3 id="multiply_fisher_factor_replicated_one_hot"><code>multiply_fisher_factor_replicated_one_hot</code></h3>

``` python
multiply_fisher_factor_replicated_one_hot(index)
```

Right-multiply a replicated-one-hot vector by a factor B of the Fisher.

Here the 'Fisher' is the Fisher information matrix (i.e. expected outer-
product of gradients) with respect to the parameters of the underlying
probability distribtion (whose log-prob defines the loss). Typically this
will be block-diagonal across different cases in the batch, since the
distribution is usually (but not always) conditionally iid across different
cases.

A 'replicated-one-hot' vector means a tensor which, for each slice along the
batch dimension (assumed to be dimension 0), is 1.0 in the entry
corresponding to the given index and 0 elsewhere.

Note that B can be any matrix satisfying B * B^T = H where H is the Fisher,
but will agree with the one used in the other methods of this class.

#### Args:

* <b>`index`</b>: A tuple representing in the index of the entry in each slice that
    is 1.0. Note that len(index) must be equal to the number of elements
    of the 'fisher_factor_inner_shape' tensor minus one.


#### Returns:

The vector right-multiplied by B. Will be of the same shape(s) as the
'inputs' property.

<h3 id="multiply_fisher_factor_transpose"><code>multiply_fisher_factor_transpose</code></h3>

``` python
multiply_fisher_factor_transpose(vecs)
```

Right-multiply a vector by the transpose of a factor B of the Fisher.

Here the 'Fisher' is the Fisher information matrix (i.e. expected outer-
product of gradients) with respect to the parameters of the underlying
probability distribtion (whose log-prob defines the loss). Typically this
will be block-diagonal across different cases in the batch, since the
distribution is usually (but not always) conditionally iid across different
cases.

Note that B can be any matrix satisfying B * B^T = F where F is the Fisher,
but will agree with the one used in the other methods of this class.

#### Args:

* <b>`vector`</b>: The vector to multiply.  Must be the same shape(s) as the
    'inputs' property.


#### Returns:

The vector right-multiplied by B^T.  Will be of the shape given by the
'fisher_factor_inner_shape' property.

<h3 id="multiply_hessian"><code>multiply_hessian</code></h3>

``` python
multiply_hessian(vector)
```

Right-multiply a vector by the Hessian.

Here the 'Hessian' is the Hessian matrix (i.e. matrix of 2nd-derivatives)
of the loss function with respect to its inputs.

#### Args:

* <b>`vector`</b>: The vector to multiply.  Must be the same shape(s) as the
    'inputs' property.


#### Returns:

The vector right-multiplied by the Hessian.  Will be of the same shape(s)
as the 'inputs' property.

<h3 id="multiply_hessian_factor"><code>multiply_hessian_factor</code></h3>

``` python
multiply_hessian_factor(vector)
```

Right-multiply a vector by a factor B of the Hessian.

Here the 'Hessian' is the Hessian matrix (i.e. matrix of 2nd-derivatives)
of the loss function with respect to its inputs.  Typically this will be
block-diagonal across different cases in the batch, since the loss function
is typically summed across cases.

Note that B can be any matrix satisfying B * B^T = H where H is the Hessian,
but will agree with the one used in the other methods of this class.

#### Args:

* <b>`vector`</b>: The vector to multiply.  Must be of the shape given by the
    'hessian_factor_inner_shape' property.


#### Returns:

The vector right-multiplied by B.  Will be of the same shape(s) as the
'inputs' property.

<h3 id="multiply_hessian_factor_replicated_one_hot"><code>multiply_hessian_factor_replicated_one_hot</code></h3>

``` python
multiply_hessian_factor_replicated_one_hot(index)
```

Right-multiply a replicated-one-hot vector by a factor B of the Hessian.

Here the 'Hessian' is the Hessian matrix (i.e. matrix of 2nd-derivatives)
of the loss function with respect to its inputs.  Typically this will be
block-diagonal across different cases in the batch, since the loss function
is typically summed across cases.

A 'replicated-one-hot' vector means a tensor which, for each slice along the
batch dimension (assumed to be dimension 0), is 1.0 in the entry
corresponding to the given index and 0 elsewhere.

Note that B can be any matrix satisfying B * B^T = H where H is the Hessian,
but will agree with the one used in the other methods of this class.

#### Args:

* <b>`index`</b>: A tuple representing in the index of the entry in each slice that
    is 1.0. Note that len(index) must be equal to the number of elements
    of the 'hessian_factor_inner_shape' tensor minus one.


#### Returns:

The vector right-multiplied by B^T. Will be of the same shape(s) as the
'inputs' property.

<h3 id="multiply_hessian_factor_transpose"><code>multiply_hessian_factor_transpose</code></h3>

``` python
multiply_hessian_factor_transpose(vector)
```

Right-multiply a vector by the transpose of a factor B of the Hessian.

Here the 'Hessian' is the Hessian matrix (i.e. matrix of 2nd-derivatives)
of the loss function with respect to its inputs.  Typically this will be
block-diagonal across different cases in the batch, since the loss function
is typically summed across cases.

Note that B can be any matrix satisfying B * B^T = H where H is the Hessian,
but will agree with the one used in the other methods of this class.

#### Args:

* <b>`vector`</b>: The vector to multiply.  Must be the same shape(s) as the
    'inputs' property.


#### Returns:

The vector right-multiplied by B^T.  Will be of the shape given by the
'hessian_factor_inner_shape' property.

<h3 id="sample"><code>sample</code></h3>

``` python
sample(seed)
```

Sample 'targets' from the underlying distribution.



