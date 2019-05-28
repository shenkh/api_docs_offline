<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distribute.Step" />
<meta itemprop="property" content="distribution"/>
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="inputs"/>
<meta itemprop="property" content="step"/>
</div>

# tf.contrib.distribute.Step

## Class `Step`





Defined in [`tensorflow/contrib/distribute/python/step_fn.py`](https://www.tensorflow.org/code/tensorflow/contrib/distribute/python/step_fn.py).

Interface for performing each step of a training algorithm.

## Properties

<h3 id="distribution"><code>distribution</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(distribution)
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



