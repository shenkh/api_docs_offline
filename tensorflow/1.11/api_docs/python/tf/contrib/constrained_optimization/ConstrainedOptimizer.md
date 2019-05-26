<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.constrained_optimization.ConstrainedOptimizer" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="optimizer"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="minimize"/>
<meta itemprop="property" content="minimize_constrained"/>
<meta itemprop="property" content="minimize_unconstrained"/>
</div>

# tf.contrib.constrained_optimization.ConstrainedOptimizer

## Class `ConstrainedOptimizer`





Defined in [`tensorflow/contrib/constrained_optimization/python/constrained_optimizer.py`](https://www.tensorflow.org/code/tensorflow/contrib/constrained_optimization/python/constrained_optimizer.py).

Base class representing a constrained optimizer.

A ConstrainedOptimizer wraps a tf.train.Optimizer (or more than one), and
applies it to a ConstrainedMinimizationProblem. Unlike a tf.train.Optimizer,
which takes a tensor to minimize as a parameter to its minimize() method, a
constrained optimizer instead takes a ConstrainedMinimizationProblem.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(optimizer)
```

Constructs a new `ConstrainedOptimizer`.

#### Args:

* <b>`optimizer`</b>: tf.train.Optimizer, used to optimize the
    ConstraintedMinimizationProblem.


#### Returns:

A new `ConstrainedOptimizer`.



## Properties

<h3 id="optimizer"><code>optimizer</code></h3>

Returns the <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a> used for optimization.



## Methods

<h3 id="minimize"><code>minimize</code></h3>

``` python
minimize(
    minimization_problem,
    unconstrained_steps=None,
    global_step=None,
    var_list=None,
    gate_gradients=train_optimizer.Optimizer.GATE_OP,
    aggregation_method=None,
    colocate_gradients_with_ops=False,
    name=None,
    grad_loss=None
)
```

Returns an `Operation` for minimizing the constrained problem.

This method combines the functionality of `minimize_unconstrained` and
`minimize_constrained`. If global_step < unconstrained_steps, it will
perform an unconstrained update, and if global_step >= unconstrained_steps,
it will perform a constrained update.

The reason for this functionality is that it may be best to initialize the
constrained optimizer with an approximate optimum of the unconstrained
problem.

#### Args:

* <b>`minimization_problem`</b>: ConstrainedMinimizationProblem, the problem to
    optimize.
* <b>`unconstrained_steps`</b>: int, number of steps for which we should perform
    unconstrained updates, before transitioning to constrained updates.
* <b>`global_step`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.
* <b>`var_list`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.
* <b>`gate_gradients`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.
* <b>`aggregation_method`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.
* <b>`colocate_gradients_with_ops`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize`
    method.
* <b>`name`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.
* <b>`grad_loss`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.


#### Returns:

`Operation`, the train_op.


#### Raises:

* <b>`ValueError`</b>: If unconstrained_steps is provided, but global_step is not.

<h3 id="minimize_constrained"><code>minimize_constrained</code></h3>

``` python
minimize_constrained(
    minimization_problem,
    global_step=None,
    var_list=None,
    gate_gradients=train_optimizer.Optimizer.GATE_OP,
    aggregation_method=None,
    colocate_gradients_with_ops=False,
    name=None,
    grad_loss=None
)
```

Returns an `Operation` for minimizing the constrained problem.

Unlike `minimize_unconstrained`, this function attempts to find a solution
that minimizes the `objective` portion of the minimization problem while
satisfying the `constraints` portion.

#### Args:

* <b>`minimization_problem`</b>: ConstrainedMinimizationProblem, the problem to
    optimize.
* <b>`global_step`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.
* <b>`var_list`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.
* <b>`gate_gradients`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.
* <b>`aggregation_method`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.
* <b>`colocate_gradients_with_ops`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize`
    method.
* <b>`name`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.
* <b>`grad_loss`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.


#### Returns:

`Operation`, the train_op.

<h3 id="minimize_unconstrained"><code>minimize_unconstrained</code></h3>

``` python
minimize_unconstrained(
    minimization_problem,
    global_step=None,
    var_list=None,
    gate_gradients=train_optimizer.Optimizer.GATE_OP,
    aggregation_method=None,
    colocate_gradients_with_ops=False,
    name=None,
    grad_loss=None
)
```

Returns an `Operation` for minimizing the unconstrained problem.

Unlike `minimize_constrained`, this function ignores the `constraints` (and
`proxy_constraints`) portion of the minimization problem entirely, and only
minimizes `objective`.

#### Args:

* <b>`minimization_problem`</b>: ConstrainedMinimizationProblem, the problem to
    optimize.
* <b>`global_step`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.
* <b>`var_list`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.
* <b>`gate_gradients`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.
* <b>`aggregation_method`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.
* <b>`colocate_gradients_with_ops`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize`
    method.
* <b>`name`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.
* <b>`grad_loss`</b>: as in <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>'s `minimize` method.


#### Returns:

`Operation`, the train_op.



