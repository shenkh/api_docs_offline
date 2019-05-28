<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distribute.StandardSingleLossStep" />
<meta itemprop="property" content="distribution"/>
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="inputs"/>
<meta itemprop="property" content="step"/>
</div>

# tf.contrib.distribute.StandardSingleLossStep

## Class `StandardSingleLossStep`

Inherits From: [`StandardInputStep`](../../../tf/contrib/distribute/StandardInputStep.md)



Defined in [`tensorflow/contrib/distribute/python/step_fn.py`](https://www.tensorflow.org/code/tensorflow/contrib/distribute/python/step_fn.py).

A step function that implements a training step for a feed forward network.

An instance of this class is intended to be used as a callable:

```python
...
step = step_fn.StandardSingleLossStep(dataset, loss_fn, optimizer)
step.initialize(distribution)

# Run a single training step on a given DistributionStrategy:
step(distribution)
...
```

#### Args:

* <b>`dataset_fn`</b>: a function that returns a tf.data Dataset that produces the
    input for the model.
* <b>`loss_fn`</b>: a function that returns loss.
* <b>`optimizer`</b>: an optimizer that implements an update rule.
* <b>`distribution`</b>: a `DistributionStrategy` object.

## Properties

<h3 id="distribution"><code>distribution</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    dataset_fn,
    loss_fn,
    optimizer,
    distribution
)
```

Initialize self.  See help(type(self)) for accurate signature.

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__()
```

Perform one step of this training algorithm.

<h3 id="inputs"><code>inputs</code></h3>

``` python
inputs()
```

For the generating the input to be passed to `step()`.

<h3 id="step"><code>step</code></h3>

``` python
step(inputs)
```

Perform the main computation of this training algorithm.



