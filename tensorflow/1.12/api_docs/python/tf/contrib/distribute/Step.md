<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distribute.Step" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="distribution"/>
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.contrib.distribute.Step

## Class `Step`





Defined in [`tensorflow/contrib/distribute/python/step_fn.py`](/code/stable/tensorflow/contrib/distribute/python/step_fn.py).

Interface for performing each step of a training algorithm.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(distribution)
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



