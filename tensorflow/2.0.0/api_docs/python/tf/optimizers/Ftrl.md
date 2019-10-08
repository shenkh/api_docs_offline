<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.optimizers.Ftrl" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="iterations"/>
<meta itemprop="property" content="weights"/>
<meta itemprop="property" content="__getattribute__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__setattr__"/>
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

# tf.optimizers.Ftrl

## Class `Ftrl`

Inherits From: [`Optimizer`](../../tf/optimizers/Optimizer.md)

### Aliases:

* Class `tf.keras.optimizers.Ftrl`
* Class `tf.optimizers.Ftrl`



Defined in [`tensorflow/python/keras/optimizer_v2/ftrl.py`](/code/stable/tensorflow/python/keras/optimizer_v2/ftrl.py).

Optimizer that implements the FTRL algorithm.

See Algorithm 1 of this [paper](
https://www.eecs.tufts.edu/~dsculley/papers/ad-click-prediction.pdf).
This version has support for both online L2 (the L2 penalty given in the paper
above) and shrinkage-type L2 (which is the addition of an L2 penalty to the
loss function).

Initialization:
$$t = 0$$
$$n_{0} = 0$$
$$\sigma_{0} = 0$$
$$z_{0} = 0$$

Update ($$i$$ is variable index):
$$t = t + 1$$
$$n_{t,i} = n_{t-1,i} + g_{t,i}^{2}$$
$$\sigma_{t,i} = (\sqrt{n_{t,i}} - \sqrt{n_{t-1,i}}) / \alpha$$
$$z_{t,i} = z_{t-1,i} + g_{t,i} - \sigma_{t,i} * w_{t,i}$$
$$w_{t,i} = - ((\beta+\sqrt{n+{t}}) / \alpha + \lambda_{2})^{-1} * (z_{i} -
             sgn(z_{i}) * \lambda_{1}) if \abs{z_{i}} > \lambda_{i} else 0$$

Check the documentation for the l2_shrinkage_regularization_strength
parameter for more details when shrinkage is enabled, where gradient is
replaced with gradient_with_shrinkage.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    learning_rate=0.001,
    learning_rate_power=-0.5,
    initial_accumulator_value=0.1,
    l1_regularization_strength=0.0,
    l2_regularization_strength=0.0,
    name='Ftrl',
    l2_shrinkage_regularization_strength=0.0,
    **kwargs
)
```

Construct a new FTRL optimizer.

#### Args:

* <b>`learning_rate`</b>: A float value or a constant float `Tensor`.
* <b>`learning_rate_power`</b>: A float value, must be less or equal to zero.
    Controls how the learning rate decreases during training. Use zero for
    a fixed learning rate.
* <b>`initial_accumulator_value`</b>: The starting value for accumulators.
    Only zero or positive values are allowed.
* <b>`l1_regularization_strength`</b>: A float value, must be greater than or
    equal to zero.
* <b>`l2_regularization_strength`</b>: A float value, must be greater than or
    equal to zero.
* <b>`name`</b>: Optional name prefix for the operations created when applying
    gradients.  Defaults to "Ftrl".
* <b>`l2_shrinkage_regularization_strength`</b>: A float value, must be greater than
    or equal to zero. This differs from L2 above in that the L2 above is a
    stabilization penalty, whereas this L2 shrinkage is a magnitude penalty.
    The FTRL formulation can be written as:
    w_{t+1} = argmin_w(\hat{g}_{1:t}w + L1*||w||_1 + L2*||w||_2^2), where
    \hat{g} = g + (2*L2_shrinkage*w), and g is the gradient of the loss
    function w.r.t. the weights w.
    Specifically, in the absence of L1 regularization, it is equivalent to
    the following update rule:
    w_{t+1} = w_t - lr_t / (1 + 2*L2*lr_t) * g_t -
              2*L2_shrinkage*lr_t / (1 + 2*L2*lr_t) * w_t
    where lr_t is the learning rate at t.
    When input is sparse shrinkage will only happen on the active weights.\
* <b>`**kwargs`</b>: keyword arguments. Allowed to be {`clipnorm`, `clipvalue`, `lr`,
    `decay`}. `clipnorm` is clip gradients by norm; `clipvalue` is clip
    gradients by value, `decay` is included for backward compatibility to
    allow time inverse decay of learning rate. `lr` is included for backward
    compatibility, recommended to use `learning_rate` instead.


#### Raises:

* <b>`ValueError`</b>: If one of the arguments is invalid.

References
  See [paper]
    (https://www.eecs.tufts.edu/~dsculley/papers/ad-click-prediction.pdf)



## Properties

<h3 id="iterations"><code>iterations</code></h3>

Variable. The number of training steps this Optimizer has run.

<h3 id="weights"><code>weights</code></h3>

Returns variables of this Optimizer based on the order created.



## Methods

<h3 id="__getattribute__"><code>__getattribute__</code></h3>

``` python
__getattribute__(name)
```

Overridden to support hyperparameter access.

<h3 id="__setattr__"><code>__setattr__</code></h3>

``` python
__setattr__(
    name,
    value
)
```

Override setattr to support dynamic hyperparameter setting.

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
    aggregation=tf_variables.VariableAggregation.NONE
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

This method simply computes gradient using <a href="../../tf/GradientTape.md"><code>tf.GradientTape</code></a> and calls
`apply_gradients()`. If you want to process the gradient before applying
then call <a href="../../tf/GradientTape.md"><code>tf.GradientTape</code></a> and `apply_gradients()` explicitly instead
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



