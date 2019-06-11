<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.LeakyReLU" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.LeakyReLU

## Class `LeakyReLU`

Leaky version of a Rectified Linear Unit.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

### Aliases:

* Class `tf.compat.v1.keras.layers.LeakyReLU`
* Class `tf.compat.v2.keras.layers.LeakyReLU`
* Class `tf.keras.layers.LeakyReLU`



Defined in [`python/keras/layers/advanced_activations.py`](/code/stable/tensorflow/python/keras/layers/advanced_activations.py).

<!-- Placeholder for "Used in" -->

It allows a small gradient when the unit is not active:
`f(x) = alpha * x for x < 0`,
`f(x) = x for x >= 0`.

#### Input shape:

Arbitrary. Use the keyword argument `input_shape`
(tuple of integers, does not include the samples axis)
when using this layer as the first layer in a model.



#### Output shape:

Same shape as the input.



#### Arguments:


* <b>`alpha`</b>: Float >= 0. Negative slope coefficient.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    alpha=0.3,
    **kwargs
)
```






