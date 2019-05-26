<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distribute.StandardInputStep" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="distribution"/>
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.contrib.distribute.StandardInputStep

## Class `StandardInputStep`

Inherits From: [`Step`](../../../tf/contrib/distribute/Step.md)



Defined in [`tensorflow/contrib/distribute/python/step_fn.py`](https://www.tensorflow.org/code/tensorflow/contrib/distribute/python/step_fn.py).

Step with a standard implementation of input handling.

#### Args:

* <b>`dataset_fn`</b>: a function that returns a tf.data Dataset that produces the
    input for the model.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    dataset_fn,
    distribution
)
```

Initialize self.  See help(type(self)) for accurate signature.



## Properties

<h3 id="distribution"><code>distribution</code></h3>





## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__()
```

Perform one step of this training algorithm.



