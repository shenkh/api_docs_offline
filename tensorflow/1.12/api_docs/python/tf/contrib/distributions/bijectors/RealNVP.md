<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distributions.bijectors.RealNVP" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="dtype"/>
<meta itemprop="property" content="forward_min_event_ndims"/>
<meta itemprop="property" content="graph_parents"/>
<meta itemprop="property" content="inverse_min_event_ndims"/>
<meta itemprop="property" content="is_constant_jacobian"/>
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="validate_args"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="forward"/>
<meta itemprop="property" content="forward_event_shape"/>
<meta itemprop="property" content="forward_event_shape_tensor"/>
<meta itemprop="property" content="forward_log_det_jacobian"/>
<meta itemprop="property" content="inverse"/>
<meta itemprop="property" content="inverse_event_shape"/>
<meta itemprop="property" content="inverse_event_shape_tensor"/>
<meta itemprop="property" content="inverse_log_det_jacobian"/>
</div>

# tf.contrib.distributions.bijectors.RealNVP

## Class `RealNVP`

Inherits From: [`Bijector`](../../../../tf/contrib/distributions/bijectors/Bijector.md)



Defined in [`tensorflow/contrib/distributions/python/ops/bijectors/real_nvp.py`](/code/stable/tensorflow/contrib/distributions/python/ops/bijectors/real_nvp.py).

RealNVP "affine coupling layer" for vector-valued events.

Real NVP models a normalizing flow on a `D`-dimensional distribution via a
single `D-d`-dimensional conditional distribution [(Dinh et al., 2017)][1]:

`y[d:D] = y[d:D] * math_ops.exp(log_scale_fn(y[d:D])) + shift_fn(y[d:D])`
`y[0:d] = x[0:d]`

The last `D-d` units are scaled and shifted based on the first `d` units only,
while the first `d` units are 'masked' and left unchanged. Real NVP's
`shift_and_log_scale_fn` computes vector-valued quantities. For
scale-and-shift transforms that do not depend on any masked units, i.e.
`d=0`, use the `tfb.Affine` bijector with learned parameters instead.

Masking is currently only supported for base distributions with
`event_ndims=1`. For more sophisticated masking schemes like checkerboard or
channel-wise masking [(Papamakarios et al., 2016)[4], use the `tfb.Permute`
bijector to re-order desired masked units into the first `d` units. For base
distributions with `event_ndims > 1`, use the `tfb.Reshape` bijector to
flatten the event shape.

Recall that the MAF bijector [(Papamakarios et al., 2016)][4] implements a
normalizing flow via an autoregressive transformation. MAF and IAF have
opposite computational tradeoffs - MAF can train all units in parallel but
must sample units sequentially, while IAF must train units sequentially but
can sample in parallel. In contrast, Real NVP can compute both forward and
inverse computations in parallel. However, the lack of an autoregressive
transformations makes it less expressive on a per-bijector basis.

A "valid" `shift_and_log_scale_fn` must compute each `shift` (aka `loc` or
"mu" in [Papamakarios et al. (2016)][4]) and `log(scale)` (aka "alpha" in
[Papamakarios et al. (2016)][4]) such that each are broadcastable with the
arguments to `forward` and `inverse`, i.e., such that the calculations in
`forward`, `inverse` [below] are possible. For convenience,
`real_nvp_default_nvp` is offered as a possible `shift_and_log_scale_fn`
function.

NICE [(Dinh et al., 2014)][2] is a special case of the Real NVP bijector
which discards the scale transformation, resulting in a constant-time
inverse-log-determinant-Jacobian. To use a NICE bijector instead of Real
NVP, `shift_and_log_scale_fn` should return `(shift, None)`, and
`is_constant_jacobian` should be set to `True` in the `RealNVP` constructor.
Calling `real_nvp_default_template` with `shift_only=True` returns one such
NICE-compatible `shift_and_log_scale_fn`.

Caching: the scalar input depth `D` of the base distribution is not known at
construction time. The first call to any of `forward(x)`, `inverse(x)`,
`inverse_log_det_jacobian(x)`, or `forward_log_det_jacobian(x)` memoizes
`D`, which is re-used in subsequent calls. This shape must be known prior to
graph execution (which is the case if using tf.layers).

#### Example Use

```python
import tensorflow_probability as tfp
tfd = tfp.distributions
tfb = tfp.bijectors

# A common choice for a normalizing flow is to use a Gaussian for the base
# distribution. (However, any continuous distribution would work.) E.g.,
nvp = tfd.TransformedDistribution(
    distribution=tfd.MultivariateNormalDiag(loc=[0., 0., 0.])),
    bijector=tfb.RealNVP(
        num_masked=2,
        shift_and_log_scale_fn=tfb.real_nvp_default_template(
            hidden_layers=[512, 512])))

x = nvp.sample()
nvp.log_prob(x)
nvp.log_prob(0.)
```

For more examples, see [Jang (2018)][3].

#### References

[1]: Laurent Dinh, Jascha Sohl-Dickstein, and Samy Bengio. Density Estimation
     using Real NVP. In _International Conference on Learning
     Representations_, 2017. https://arxiv.org/abs/1605.08803

[2]: Laurent Dinh, David Krueger, and Yoshua Bengio. NICE: Non-linear
     Independent Components Estimation. _arXiv preprint arXiv:1410.8516_,
     2014. https://arxiv.org/abs/1410.8516

[3]: Eric Jang. Normalizing Flows Tutorial, Part 2: Modern Normalizing Flows.
     _Technical Report_, 2018. http://blog.evjang.com/2018/01/nf2.html

[4]: George Papamakarios, Theo Pavlakou, and Iain Murray. Masked
     Autoregressive Flow for Density Estimation. In _Neural Information
     Processing Systems_, 2017. https://arxiv.org/abs/1705.07057

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    num_masked,
    shift_and_log_scale_fn,
    is_constant_jacobian=False,
    validate_args=False,
    name=None
)
```

Creates the Real NVP or NICE bijector. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed after 2018-10-01.
Instructions for updating:
The TensorFlow Distributions library has moved to TensorFlow Probability (https://github.com/tensorflow/probability). You should update all references to use `tfp.distributions` instead of <a href="../../../../tf/contrib/distributions.md"><code>tf.contrib.distributions</code></a>.

#### Args:

* <b>`num_masked`</b>: Python `int` indicating that the first `d` units of the event
    should be masked. Must be in the closed interval `[1, D-1]`, where `D`
    is the event size of the base distribution.
* <b>`shift_and_log_scale_fn`</b>: Python `callable` which computes `shift` and
    `log_scale` from both the forward domain (`x`) and the inverse domain
    (`y`). Calculation must respect the "autoregressive property" (see class
    docstring). Suggested default
    `masked_autoregressive_default_template(hidden_layers=...)`.
    Typically the function contains `tf.Variables` and is wrapped using
    <a href="../../../../tf/make_template.md"><code>tf.make_template</code></a>. Returning `None` for either (both) `shift`,
    `log_scale` is equivalent to (but more efficient than) returning zero.
* <b>`is_constant_jacobian`</b>: Python `bool`. Default: `False`. When `True` the
    implementation assumes `log_scale` does not depend on the forward domain
    (`x`) or inverse domain (`y`) values. (No validation is made;
    `is_constant_jacobian=False` is always safe but possibly computationally
    inefficient.)
* <b>`validate_args`</b>: Python `bool` indicating whether arguments should be
    checked for correctness.
* <b>`name`</b>: Python `str`, name given to ops managed by this object.


#### Raises:

* <b>`ValueError`</b>: If num_masked < 1.



## Properties

<h3 id="dtype"><code>dtype</code></h3>

dtype of `Tensor`s transformable by this distribution.

<h3 id="forward_min_event_ndims"><code>forward_min_event_ndims</code></h3>

Returns the minimal number of dimensions bijector.forward operates on.

<h3 id="graph_parents"><code>graph_parents</code></h3>

Returns this `Bijector`'s graph_parents as a Python list.

<h3 id="inverse_min_event_ndims"><code>inverse_min_event_ndims</code></h3>

Returns the minimal number of dimensions bijector.inverse operates on.

<h3 id="is_constant_jacobian"><code>is_constant_jacobian</code></h3>

Returns true iff the Jacobian matrix is not a function of x.

Note: Jacobian matrix is either constant for both forward and inverse or
neither.

#### Returns:

* <b>`is_constant_jacobian`</b>: Python `bool`.

<h3 id="name"><code>name</code></h3>

Returns the string name of this `Bijector`.

<h3 id="validate_args"><code>validate_args</code></h3>

Returns True if Tensor arguments will be validated.



## Methods

<h3 id="forward"><code>forward</code></h3>

``` python
forward(
    x,
    name='forward'
)
```

Returns the forward `Bijector` evaluation, i.e., X = g(Y).

#### Args:

* <b>`x`</b>: `Tensor`. The input to the "forward" evaluation.
* <b>`name`</b>: The name to give this op.


#### Returns:

`Tensor`.


#### Raises:

* <b>`TypeError`</b>: if `self.dtype` is specified and `x.dtype` is not
    `self.dtype`.
* <b>`NotImplementedError`</b>: if `_forward` is not implemented.

<h3 id="forward_event_shape"><code>forward_event_shape</code></h3>

``` python
forward_event_shape(input_shape)
```

Shape of a single sample from a single batch as a `TensorShape`.

Same meaning as `forward_event_shape_tensor`. May be only partially defined.

#### Args:

* <b>`input_shape`</b>: `TensorShape` indicating event-portion shape passed into
    `forward` function.


#### Returns:

* <b>`forward_event_shape_tensor`</b>: `TensorShape` indicating event-portion shape
    after applying `forward`. Possibly unknown.

<h3 id="forward_event_shape_tensor"><code>forward_event_shape_tensor</code></h3>

``` python
forward_event_shape_tensor(
    input_shape,
    name='forward_event_shape_tensor'
)
```

Shape of a single sample from a single batch as an `int32` 1D `Tensor`.

#### Args:

* <b>`input_shape`</b>: `Tensor`, `int32` vector indicating event-portion shape
    passed into `forward` function.
* <b>`name`</b>: name to give to the op


#### Returns:

* <b>`forward_event_shape_tensor`</b>: `Tensor`, `int32` vector indicating
    event-portion shape after applying `forward`.

<h3 id="forward_log_det_jacobian"><code>forward_log_det_jacobian</code></h3>

``` python
forward_log_det_jacobian(
    x,
    event_ndims,
    name='forward_log_det_jacobian'
)
```

Returns both the forward_log_det_jacobian.

#### Args:

* <b>`x`</b>: `Tensor`. The input to the "forward" Jacobian determinant evaluation.
* <b>`event_ndims`</b>: Number of dimensions in the probabilistic events being
    transformed. Must be greater than or equal to
    `self.forward_min_event_ndims`. The result is summed over the final
    dimensions to produce a scalar Jacobian determinant for each event,
    i.e. it has shape `x.shape.ndims - event_ndims` dimensions.
* <b>`name`</b>: The name to give this op.


#### Returns:

`Tensor`, if this bijector is injective.
  If not injective this is not implemented.


#### Raises:

* <b>`TypeError`</b>: if `self.dtype` is specified and `y.dtype` is not
    `self.dtype`.
* <b>`NotImplementedError`</b>: if neither `_forward_log_det_jacobian`
    nor {`_inverse`, `_inverse_log_det_jacobian`} are implemented, or
    this is a non-injective bijector.

<h3 id="inverse"><code>inverse</code></h3>

``` python
inverse(
    y,
    name='inverse'
)
```

Returns the inverse `Bijector` evaluation, i.e., X = g^{-1}(Y).

#### Args:

* <b>`y`</b>: `Tensor`. The input to the "inverse" evaluation.
* <b>`name`</b>: The name to give this op.


#### Returns:

`Tensor`, if this bijector is injective.
  If not injective, returns the k-tuple containing the unique
  `k` points `(x1, ..., xk)` such that `g(xi) = y`.


#### Raises:

* <b>`TypeError`</b>: if `self.dtype` is specified and `y.dtype` is not
    `self.dtype`.
* <b>`NotImplementedError`</b>: if `_inverse` is not implemented.

<h3 id="inverse_event_shape"><code>inverse_event_shape</code></h3>

``` python
inverse_event_shape(output_shape)
```

Shape of a single sample from a single batch as a `TensorShape`.

Same meaning as `inverse_event_shape_tensor`. May be only partially defined.

#### Args:

* <b>`output_shape`</b>: `TensorShape` indicating event-portion shape passed into
    `inverse` function.


#### Returns:

* <b>`inverse_event_shape_tensor`</b>: `TensorShape` indicating event-portion shape
    after applying `inverse`. Possibly unknown.

<h3 id="inverse_event_shape_tensor"><code>inverse_event_shape_tensor</code></h3>

``` python
inverse_event_shape_tensor(
    output_shape,
    name='inverse_event_shape_tensor'
)
```

Shape of a single sample from a single batch as an `int32` 1D `Tensor`.

#### Args:

* <b>`output_shape`</b>: `Tensor`, `int32` vector indicating event-portion shape
    passed into `inverse` function.
* <b>`name`</b>: name to give to the op


#### Returns:

* <b>`inverse_event_shape_tensor`</b>: `Tensor`, `int32` vector indicating
    event-portion shape after applying `inverse`.

<h3 id="inverse_log_det_jacobian"><code>inverse_log_det_jacobian</code></h3>

``` python
inverse_log_det_jacobian(
    y,
    event_ndims,
    name='inverse_log_det_jacobian'
)
```

Returns the (log o det o Jacobian o inverse)(y).

Mathematically, returns: `log(det(dX/dY))(Y)`. (Recall that: `X=g^{-1}(Y)`.)

Note that `forward_log_det_jacobian` is the negative of this function,
evaluated at `g^{-1}(y)`.

#### Args:

* <b>`y`</b>: `Tensor`. The input to the "inverse" Jacobian determinant evaluation.
* <b>`event_ndims`</b>: Number of dimensions in the probabilistic events being
    transformed. Must be greater than or equal to
    `self.inverse_min_event_ndims`. The result is summed over the final
    dimensions to produce a scalar Jacobian determinant for each event,
    i.e. it has shape `y.shape.ndims - event_ndims` dimensions.
* <b>`name`</b>: The name to give this op.


#### Returns:

`Tensor`, if this bijector is injective.
  If not injective, returns the tuple of local log det
  Jacobians, `log(det(Dg_i^{-1}(y)))`, where `g_i` is the restriction
  of `g` to the `ith` partition `Di`.


#### Raises:

* <b>`TypeError`</b>: if `self.dtype` is specified and `y.dtype` is not
    `self.dtype`.
* <b>`NotImplementedError`</b>: if `_inverse_log_det_jacobian` is not implemented.



