<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.optimizers.SGD" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
<meta itemprop="property" content="get_gradients"/>
<meta itemprop="property" content="get_updates"/>
<meta itemprop="property" content="get_weights"/>
<meta itemprop="property" content="set_weights"/>
</div>

# tf.keras.optimizers.SGD

## Class `SGD`

Inherits From: [`Optimizer`](../../../tf/keras/optimizers/Optimizer.md)



Defined in [`tensorflow/python/keras/optimizers.py`](https://www.tensorflow.org/code/tensorflow/python/keras/optimizers.py).

Stochastic gradient descent optimizer.

Includes support for momentum,
learning rate decay, and Nesterov momentum.

#### Arguments:

* <b>`lr`</b>: float >= 0. Learning rate.
* <b>`momentum`</b>: float >= 0. Parameter that accelerates SGD
        in the relevant direction and dampens oscillations.
* <b>`decay`</b>: float >= 0. Learning rate decay over each update.
* <b>`nesterov`</b>: boolean. Whether to apply Nesterov momentum.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    lr=0.01,
    momentum=0.0,
    decay=0.0,
    nesterov=False,
    **kwargs
)
```

Initialize self.  See help(type(self)) for accurate signature.



## Methods

<h3 id="from_config"><code>from_config</code></h3>

``` python
from_config(
    cls,
    config
)
```



<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```



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

Returns the current value of the weights of the optimizer.

#### Returns:

A list of numpy arrays.

<h3 id="set_weights"><code>set_weights</code></h3>

``` python
set_weights(weights)
```

Sets the weights of the optimizer, from Numpy arrays.

Should only be called after computing the gradients
(otherwise the optimizer has no weights).

#### Arguments:

* <b>`weights`</b>: a list of Numpy arrays. The number
        of arrays and their shape must match
        number of the dimensions of the weights
        of the optimizer (i.e. it should match the
        output of `get_weights`).


#### Raises:

* <b>`ValueError`</b>: in case of incompatible weight shapes.



