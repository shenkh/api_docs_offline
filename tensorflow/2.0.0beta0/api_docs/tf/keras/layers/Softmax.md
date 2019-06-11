<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.Softmax" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.Softmax

## Class `Softmax`

Softmax activation function.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

### Aliases:

* Class `tf.compat.v1.keras.layers.Softmax`
* Class `tf.compat.v2.keras.layers.Softmax`
* Class `tf.keras.layers.Softmax`



Defined in [`python/keras/layers/advanced_activations.py`](/code/stable/tensorflow/python/keras/layers/advanced_activations.py).

<!-- Placeholder for "Used in" -->


#### Input shape:

Arbitrary. Use the keyword argument `input_shape`
(tuple of integers, does not include the samples axis)
when using this layer as the first layer in a model.



#### Output shape:

Same shape as the input.



#### Arguments:


* <b>`axis`</b>: Integer, axis along which the softmax normalization is applied.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    axis=-1,
    **kwargs
)
```






