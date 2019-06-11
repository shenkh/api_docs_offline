<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.ELU" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.ELU

## Class `ELU`

Exponential Linear Unit.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

### Aliases:

* Class `tf.compat.v1.keras.layers.ELU`
* Class `tf.compat.v2.keras.layers.ELU`
* Class `tf.keras.layers.ELU`



Defined in [`python/keras/layers/advanced_activations.py`](/code/stable/tensorflow/python/keras/layers/advanced_activations.py).

<!-- Placeholder for "Used in" -->


#### It follows:


`f(x) =  alpha * (exp(x) - 1.) for x < 0`,
`f(x) = x for x >= 0`.

#### Input shape:

Arbitrary. Use the keyword argument `input_shape`
(tuple of integers, does not include the samples axis)
when using this layer as the first layer in a model.



#### Output shape:

Same shape as the input.



#### Arguments:


* <b>`alpha`</b>: Scale for the negative factor.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    alpha=1.0,
    **kwargs
)
```






