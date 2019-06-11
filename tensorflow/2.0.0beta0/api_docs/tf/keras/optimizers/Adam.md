<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.optimizers.Adam" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="iterations"/>
<meta itemprop="property" content="weights"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="add_slot"/>
<meta itemprop="property" content="add_weight"/>
<meta itemprop="property" content="apply_gradients"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
<meta itemprop="property" content="get_gradients"/>
<meta itemprop="property" content="get_slot"/>
<meta itemprop="property" content="get_slot_names"/>
<meta itemprop="property" content="get_updates"/>
<meta itemprop="property" content="get_weights"/>
<meta itemprop="property" content="minimize"/>
<meta itemprop="property" content="set_weights"/>
<meta itemprop="property" content="variables"/>
</div>

# tf.keras.optimizers.Adam

## Class `Adam`

Optimizer that implements the Adam algorithm.

Inherits From: [`Optimizer`](../../../tf/keras/optimizers/Optimizer.md)

### Aliases:

* Class `tf.compat.v1.keras.optimizers.Adam`
* Class `tf.compat.v2.keras.optimizers.Adam`
* Class `tf.compat.v2.optimizers.Adam`
* Class `tf.keras.optimizers.Adam`
* Class `tf.optimizers.Adam`



Defined in [`python/keras/optimizer_v2/adam.py`](/code/stable/tensorflow/python/keras/optimizer_v2/adam.py).

<!-- Placeholder for "Used in" -->

Adam optimization is a stochastic gradient descent method that is based on
adaptive estimation of first-order and second-order moments.
According to the paper
[Adam: A Method for Stochastic Optimization. Kingma et al.,
2014](http://arxiv.org/abs/1412.6980),
 the method is "*computationally efficient, has little memory
requirement, invariant to diagonal rescaling of gradients, and is well suited
for problems that are large in terms of data/parameters*".

For AMSGrad see [On The Convergence Of Adam And Beyond.
Reddi et al., 5-8](https://openreview.net/pdf?id=ryQu7f-RZ).

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    learning_rate=0.001,
    beta_1=0.9,
    beta_2=0.999,
    epsilon=1e-07,
    amsgrad=False,
    name='Adam',
    **kwargs
)
```

Construct a new Adam optimizer.

If amsgrad = False:
  Initialization:

  $$m_0 := 0 \text{(Initialize initial 1st moment vector)}$$
  $$v_0 := 0 \text{(Initialize initial 2nd moment vector)}$$
  $$t := 0 \text{(Initialize timestep)}$$

  The update rule for `variable` with gradient `g` uses an optimization
  described at the end of section 2 of the paper:

  $$t := t + 1$$
  $$lr_t := \text{learning\_rate} * \sqrt{1 - beta_2^t} / (1 - beta_1^t)$$

  $$m_t := beta_1 * m_{t-1} + (1 - beta_1) * g$$
  $$v_t := beta_2 * v_{t-1} + (1 - beta_2) * g * g$$
  $$variable := variable - lr_t * m_t / (\sqrt{v_t} + \epsilon)$$

If amsgrad = True:
  Initialization:

  $$m_0 := 0 \text{(Initialize initial 1st moment vector)}$$
  $$v_0 := 0 \text{(Initialize initial 2nd moment vector)}$$
  $$v_hat_0 := 0 \text{(Initialize initial 2nd moment vector)}$$
  $$t := 0 \text{(Initialize timestep)}$$

  The update rule for `variable` with gradient `g` uses an optimization
  described at the end of section 2 of the paper:

  $$t := t + 1$$
  $$lr_t := \text{learning\_rate} * \sqrt{1 - beta_2^t} / (1 - beta_1^t)$$

  $$m_t := beta_1 * m_{t-1} + (1 - beta_1) * g$$
  $$v_t := beta_2 * v_{t-1} + (1 - beta_2) * g * g$$
  $$v_hat_t := max(v_hat_{t-1}, v_t)
  $$variable := variable - lr_t * m_t / (\sqrt{v_hat_t} + \epsilon)$$

The default value of 1e-7 for epsilon might not be a good default in
general. For example, when training an Inception network on ImageNet a
current good choice is 1.0 or 0.1. Note that since AdamOptimizer uses the
formulation just before Section 2.1 of the Kingma and Ba paper rather than
the formulation in Algorithm 1, the "epsilon" referred to here is "epsilon
hat" in the paper.

The sparse implementation of this algorithm (used when the gradient is an
IndexedSlices object, typically because of <a href="../../../tf/gather.md"><code>tf.gather</code></a> or an embedding
lookup in the forward pass) does apply momentum to variable slices even if
they were not used in the forward pass (meaning they have a gradient equal
to zero). Momentum decay (beta1) is also applied to the entire momentum
accumulator. This means that the sparse behavior is equivalent to the dense
behavior (in contrast to some momentum implementations which ignore momentum
unless a variable slice was actually used).

#### Args:


* <b>`learning_rate`</b>: A Tensor or a floating point value.  The learning rate.
* <b>`beta_1`</b>: A float value or a constant float tensor. The exponential decay
  rate for the 1st moment estimates.
* <b>`beta_2`</b>: A float value or a constant float tensor. The exponential decay
  rate for the 2nd moment estimates.
* <b>`epsilon`</b>: A small constant for numerical stability. This epsilon is
  "epsilon hat" in the Kingma and Ba paper (in the formula just before
  Section 2.1), not the epsilon in Algorithm 1 of the paper.
* <b>`amsgrad`</b>: boolean. Whether to apply AMSGrad variant of this algorithm from
  the paper "On the Convergence of Adam and beyond".
* <b>`name`</b>: Optional name for the operations created when applying gradients.
  Defaults to "Adam".  @compatibility(eager) When eager execution is
  enabled, `learning_rate`, `beta_1`, `beta_2`, and `epsilon` can each be
  a callable that takes no arguments and returns the actual value to use.
  This can be useful for changing these values across different
  invocations of optimizer functions. @end_compatibility
* <b>`**kwargs`</b>: keyword arguments. Allowed to be {`clipnorm`, `clipvalue`, `lr`,
  `decay`}. `clipnorm` is clip gradients by norm; `clipvalue` is clip
  gradients by value, `decay` is included for backward compatibility to
  allow time inverse decay of learning rate. `lr` is included for backward
  compatibility, recommended to use `learning_rate` instead.



## Properties

<h3 id="iterations"><code>iterations</code></h3>

Variable. The number of training steps this Optimizer has run.


<h3 id="weights"><code>weights</code></h3>

Returns variables of this Optimizer based on the order created.




## Methods

<h3 id="add_slot"><code>add_slot</code></h3>

``` python
add_slot(
    var,
    slot_name,
    initializer='zeros'
)
```

Add a new slot variable for `var`.


<h3 id="add_weight"><code>add_weight</code></h3>

``` python
add_weight(
    name,
    shape,
    dtype=None,
    initializer='zeros',
    trainable=None,
    synchronization=tf.VariableSynchronization.AUTO,
    aggregation=tf.compat.v1.VariableAggregation.NONE
)
```




<h3 id="apply_gradients"><code>apply_gradients</code></h3>

``` python
apply_gradients(
    grads_and_vars,
    name=None
)
```

Apply gradients to variables.

This is the second part of `minimize()`. It returns an `Operation` that
applies gradients.

#### Args:


* <b>`grads_and_vars`</b>: List of (gradient, variable) pairs.
* <b>`name`</b>: Optional name for the returned operation.  Default to the name
  passed to the `Optimizer` constructor.


#### Returns:

An `Operation` that applies the specified gradients. If `global_step`
was not None, that operation also increments `global_step`.



#### Raises:


* <b>`TypeError`</b>: If `grads_and_vars` is malformed.
* <b>`ValueError`</b>: If none of the variables have gradients.

<h3 id="from_config"><code>from_config</code></h3>

``` python
from_config(
    cls,
    config,
    custom_objects=None
)
```

Creates an optimizer from its config.

This method is the reverse of `get_config`,
capable of instantiating the same optimizer from the config
dictionary.

#### Arguments:


* <b>`config`</b>: A Python dictionary, typically the output of get_config.
* <b>`custom_objects`</b>: A Python dictionary mapping names to additional Python
  objects used to create this optimizer, such as a function used for a
  hyperparameter.


#### Returns:

An optimizer instance.


<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```

Returns the config of the optimimizer.

An optimizer config is a Python dictionary (serializable)
containing the configuration of an optimizer.
The same optimizer can be reinstantiated later
(without any saved state) from this configuration.

#### Returns:

Python dictionary.


<h3 id="get_gradients"><code>get_gradients</code></h3>

``` python
get_gradients(
    loss,
    params
)
```

Returns gradients of `loss` with respect to `params`.


#### Arguments:


* <b>`loss`</b>: Loss tensor.
* <b>`params`</b>: List of variables.


#### Returns:

List of gradient tensors.



#### Raises:


* <b>`ValueError`</b>: In case any gradient cannot be computed (e.g. if gradient
  function not implemented).

<h3 id="get_slot"><code>get_slot</code></h3>

``` python
get_slot(
    var,
    slot_name
)
```




<h3 id="get_slot_names"><code>get_slot_names</code></h3>

``` python
get_slot_names()
```

A list of names for this optimizer's slots.


<h3 id="get_updates"><code>get_updates</code></h3>

``` python
get_updates(
    loss,
    params
)
```




<h3 id="get_weights"><code>get_weights</code></h3>

``` python
get_weights()
```




<h3 id="minimize"><code>minimize</code></h3>

``` python
minimize(
    loss,
    var_list,
    grad_loss=None,
    name=None
)
```

Minimize `loss` by updating `var_list`.

This method simply computes gradient using <a href="../../../tf/GradientTape.md"><code>tf.GradientTape</code></a> and calls
`apply_gradients()`. If you want to process the gradient before applying
then call <a href="../../../tf/GradientTape.md"><code>tf.GradientTape</code></a> and `apply_gradients()` explicitly instead
of using this function.

#### Args:


* <b>`loss`</b>: A callable taking no arguments which returns the value to minimize.
* <b>`var_list`</b>: list or tuple of `Variable` objects to update to minimize
  `loss`, or a callable returning the list or tuple of `Variable` objects.
  Use callable when the variable list would otherwise be incomplete before
  `minimize` since the variables are created at the first time `loss` is
  called.
* <b>`grad_loss`</b>: Optional. A `Tensor` holding the gradient computed for `loss`.
* <b>`name`</b>: Optional name for the returned operation.


#### Returns:

An Operation that updates the variables in `var_list`.  If `global_step`
was not `None`, that operation also increments `global_step`.



#### Raises:


* <b>`ValueError`</b>: If some of the variables are not `Variable` objects.

<h3 id="set_weights"><code>set_weights</code></h3>

``` python
set_weights(weights)
```




<h3 id="variables"><code>variables</code></h3>

``` python
variables()
```

Returns variables of this Optimizer based on the order created.




