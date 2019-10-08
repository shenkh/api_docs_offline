<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.optimizers.Nadam" />
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

# tf.optimizers.Nadam

## Class `Nadam`

Inherits From: [`Optimizer`](../../tf/optimizers/Optimizer.md)

### Aliases:

* Class `tf.keras.optimizers.Nadam`
* Class `tf.optimizers.Nadam`



Defined in [`tensorflow/python/keras/optimizer_v2/nadam.py`](/code/stable/tensorflow/python/keras/optimizer_v2/nadam.py).

Optimizer that implements the NAdam algorithm.

Much like Adam is essentially RMSprop with momentum, Nadam is Adam with
Nesterov momentum.

Initialization:

$$m_0 := 0 \text{(Initialize 1st moment vector)}$$
$$v_0 := 0 \text{(Initialize 2nd moment vector)}$$
$$mu_0 := 1$$
$$t := 0 \text{(Initialize timestep)}$$

Computes:
$$t := t + 1$$
$$\mu_t := \beta_1 * (1 - 0.5 * 0.96^{0.004 * t})$$
$$g' := g / (1 - \prod_{i=1}^{t}{\mu_i})$$
$$m_t := \beta_1 * m_{t-1} + (1 - \beta_1) * g$$
$$m' := m_t / (1 - \prod_{i=1}^{t+1}{\mu_i})$$
$$v_t := \beta_2 * v_{t-1} + (1 - \beta_2) * g * g$$
$$v' := v_t / (1 - \beta_2^t)$$
$$\bar{m} := (1 - \mu_t) * g' + \mu_{t+1} * m'$$
$$\theta_t := \theta_{t-1} - lr * \bar{m} / (\sqrt{v'} + \epsilon)$$

gradient is evaluated at theta(t) + momentum * v(t), and the variables always
store theta + beta_1 * m / sqrt(v) instead of theta.

References
  See [Dozat, T., 2015](http://cs229.stanford.edu/proj2015/054_report.pdf).

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    learning_rate=0.001,
    beta_1=0.9,
    beta_2=0.999,
    epsilon=1e-07,
    name='Nadam',
    **kwargs
)
```

Construct a new Nadam optimizer.

#### Args:

* <b>`learning_rate`</b>: A Tensor or a floating point value.  The learning rate.
* <b>`beta_1`</b>: A float value or a constant float tensor. The exponential decay
    rate for the 1st moment estimates.
* <b>`beta_2`</b>: A float value or a constant float tensor. The exponential decay
    rate for the exponentially weighted infinity norm.
* <b>`epsilon`</b>: A small constant for numerical stability.
* <b>`name`</b>: Optional name for the operations created when applying gradients.
    Defaults to "Adamax".
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



