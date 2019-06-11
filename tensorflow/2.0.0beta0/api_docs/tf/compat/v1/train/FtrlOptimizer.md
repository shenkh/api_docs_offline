<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.train.FtrlOptimizer" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="apply_gradients"/>
<meta itemprop="property" content="compute_gradients"/>
<meta itemprop="property" content="get_name"/>
<meta itemprop="property" content="get_slot"/>
<meta itemprop="property" content="get_slot_names"/>
<meta itemprop="property" content="minimize"/>
<meta itemprop="property" content="variables"/>
<meta itemprop="property" content="GATE_GRAPH"/>
<meta itemprop="property" content="GATE_NONE"/>
<meta itemprop="property" content="GATE_OP"/>
</div>

# tf.compat.v1.train.FtrlOptimizer

## Class `FtrlOptimizer`

Optimizer that implements the FTRL algorithm.

Inherits From: [`Optimizer`](../../../../tf/compat/v1/train/Optimizer.md)



Defined in [`python/training/ftrl.py`](/code/stable/tensorflow/python/training/ftrl.py).

<!-- Placeholder for "Used in" -->

See this [paper](
https://www.eecs.tufts.edu/~dsculley/papers/ad-click-prediction.pdf).
This version has support for both online L2 (the L2 penalty given in the paper
above) and shrinkage-type L2 (which is the addition of an L2 penalty to the
loss function).

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    learning_rate,
    learning_rate_power=-0.5,
    initial_accumulator_value=0.1,
    l1_regularization_strength=0.0,
    l2_regularization_strength=0.0,
    use_locking=False,
    name='Ftrl',
    accum_name=None,
    linear_name=None,
    l2_shrinkage_regularization_strength=0.0
)
```

Construct a new FTRL optimizer.


#### Args:


* <b>`learning_rate`</b>: A float value or a constant float `Tensor`.
* <b>`learning_rate_power`</b>: A float value, must be less or equal to zero.
  Controls how the learning rate decreases during training. Use zero for
  a fixed learning rate. See section 3.1 in the
  [paper](https://www.eecs.tufts.edu/~dsculley/papers/ad-click-prediction.pdf).
* <b>`initial_accumulator_value`</b>: The starting value for accumulators.
  Only zero or positive values are allowed.
* <b>`l1_regularization_strength`</b>: A float value, must be greater than or
  equal to zero.
* <b>`l2_regularization_strength`</b>: A float value, must be greater than or
  equal to zero.
* <b>`use_locking`</b>: If `True` use locks for update operations.
* <b>`name`</b>: Optional name prefix for the operations created when applying
  gradients.  Defaults to "Ftrl".
* <b>`accum_name`</b>: The suffix for the variable that keeps the gradient squared
  accumulator.  If not present, defaults to name.
* <b>`linear_name`</b>: The suffix for the variable that keeps the linear gradient
  accumulator.  If not present, defaults to name + "_1".
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
  When input is sparse shrinkage will only happen on the active weights.


#### Raises:


* <b>`ValueError`</b>: If one of the arguments is invalid.



## Methods

<h3 id="apply_gradients"><code>apply_gradients</code></h3>

``` python
apply_gradients(
    grads_and_vars,
    global_step=None,
    name=None
)
```

Apply gradients to variables.

This is the second part of `minimize()`. It returns an `Operation` that
applies gradients.

#### Args:


* <b>`grads_and_vars`</b>: List of (gradient, variable) pairs as returned by
  `compute_gradients()`.
* <b>`global_step`</b>: Optional `Variable` to increment by one after the
  variables have been updated.
* <b>`name`</b>: Optional name for the returned operation.  Default to the
  name passed to the `Optimizer` constructor.


#### Returns:

An `Operation` that applies the specified gradients. If `global_step`
was not None, that operation also increments `global_step`.



#### Raises:


* <b>`TypeError`</b>: If `grads_and_vars` is malformed.
* <b>`ValueError`</b>: If none of the variables have gradients.
* <b>`RuntimeError`</b>: If you should use `_distributed_apply()` instead.

<h3 id="compute_gradients"><code>compute_gradients</code></h3>

``` python
compute_gradients(
    loss,
    var_list=None,
    gate_gradients=GATE_OP,
    aggregation_method=None,
    colocate_gradients_with_ops=False,
    grad_loss=None
)
```

Compute gradients of `loss` for the variables in `var_list`.

This is the first part of `minimize()`.  It returns a list
of (gradient, variable) pairs where "gradient" is the gradient
for "variable".  Note that "gradient" can be a `Tensor`, an
`IndexedSlices`, or `None` if there is no gradient for the
given variable.

#### Args:


* <b>`loss`</b>: A Tensor containing the value to minimize or a callable taking
  no arguments which returns the value to minimize. When eager execution
  is enabled it must be a callable.
* <b>`var_list`</b>: Optional list or tuple of <a href="../../../../tf/Variable.md"><code>tf.Variable</code></a> to update to minimize
  `loss`.  Defaults to the list of variables collected in the graph
  under the key `GraphKeys.TRAINABLE_VARIABLES`.
* <b>`gate_gradients`</b>: How to gate the computation of gradients.  Can be
  `GATE_NONE`, `GATE_OP`, or `GATE_GRAPH`.
* <b>`aggregation_method`</b>: Specifies the method used to combine gradient terms.
  Valid values are defined in the class `AggregationMethod`.
* <b>`colocate_gradients_with_ops`</b>: If True, try colocating gradients with
  the corresponding op.
* <b>`grad_loss`</b>: Optional. A `Tensor` holding the gradient computed for `loss`.


#### Returns:

A list of (gradient, variable) pairs. Variable is always present, but
gradient can be `None`.



#### Raises:


* <b>`TypeError`</b>: If `var_list` contains anything else than `Variable` objects.
* <b>`ValueError`</b>: If some arguments are invalid.
* <b>`RuntimeError`</b>: If called with eager execution enabled and `loss` is
  not callable.



#### Eager Compatibility
When eager execution is enabled, `gate_gradients`, `aggregation_method`,
and `colocate_gradients_with_ops` are ignored.



<h3 id="get_name"><code>get_name</code></h3>

``` python
get_name()
```




<h3 id="get_slot"><code>get_slot</code></h3>

``` python
get_slot(
    var,
    name
)
```

Return a slot named `name` created for `var` by the Optimizer.

Some `Optimizer` subclasses use additional variables.  For example
`Momentum` and `Adagrad` use variables to accumulate updates.  This method
gives access to these `Variable` objects if for some reason you need them.

Use `get_slot_names()` to get the list of slot names created by the
`Optimizer`.

#### Args:


* <b>`var`</b>: A variable passed to `minimize()` or `apply_gradients()`.
* <b>`name`</b>: A string.


#### Returns:

The `Variable` for the slot if it was created, `None` otherwise.


<h3 id="get_slot_names"><code>get_slot_names</code></h3>

``` python
get_slot_names()
```

Return a list of the names of slots created by the `Optimizer`.

See `get_slot()`.

#### Returns:

A list of strings.


<h3 id="minimize"><code>minimize</code></h3>

``` python
minimize(
    loss,
    global_step=None,
    var_list=None,
    gate_gradients=GATE_OP,
    aggregation_method=None,
    colocate_gradients_with_ops=False,
    name=None,
    grad_loss=None
)
```

Add operations to minimize `loss` by updating `var_list`.

This method simply combines calls `compute_gradients()` and
`apply_gradients()`. If you want to process the gradient before applying
them call `compute_gradients()` and `apply_gradients()` explicitly instead
of using this function.

#### Args:


* <b>`loss`</b>: A `Tensor` containing the value to minimize.
* <b>`global_step`</b>: Optional `Variable` to increment by one after the
  variables have been updated.
* <b>`var_list`</b>: Optional list or tuple of `Variable` objects to update to
  minimize `loss`.  Defaults to the list of variables collected in
  the graph under the key `GraphKeys.TRAINABLE_VARIABLES`.
* <b>`gate_gradients`</b>: How to gate the computation of gradients.  Can be
  `GATE_NONE`, `GATE_OP`, or  `GATE_GRAPH`.
* <b>`aggregation_method`</b>: Specifies the method used to combine gradient terms.
  Valid values are defined in the class `AggregationMethod`.
* <b>`colocate_gradients_with_ops`</b>: If True, try colocating gradients with
  the corresponding op.
* <b>`name`</b>: Optional name for the returned operation.
* <b>`grad_loss`</b>: Optional. A `Tensor` holding the gradient computed for `loss`.


#### Returns:

An Operation that updates the variables in `var_list`.  If `global_step`
was not `None`, that operation also increments `global_step`.



#### Raises:


* <b>`ValueError`</b>: If some of the variables are not `Variable` objects.



#### Eager Compatibility
When eager execution is enabled, `loss` should be a Python function that
takes no arguments and computes the value to be minimized. Minimization (and
gradient computation) is done with respect to the elements of `var_list` if
not None, else with respect to any trainable variables created during the
execution of the `loss` function. `gate_gradients`, `aggregation_method`,
`colocate_gradients_with_ops` and `grad_loss` are ignored when eager
execution is enabled.



<h3 id="variables"><code>variables</code></h3>

``` python
variables()
```

A list of variables which encode the current state of `Optimizer`.

Includes slot variables and additional global variables created by the
optimizer in the current default graph.

#### Returns:

A list of variables.




## Class Members

* `GATE_GRAPH = 2` <a id="GATE_GRAPH"></a>
* `GATE_NONE = 0` <a id="GATE_NONE"></a>
* `GATE_OP = 1` <a id="GATE_OP"></a>
