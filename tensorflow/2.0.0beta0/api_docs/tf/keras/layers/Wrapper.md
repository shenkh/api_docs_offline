<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.Wrapper" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.Wrapper

## Class `Wrapper`

Abstract wrapper base class.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

### Aliases:

* Class `tf.compat.v1.keras.layers.Wrapper`
* Class `tf.compat.v2.keras.layers.Wrapper`
* Class `tf.keras.layers.Wrapper`



Defined in [`python/keras/layers/wrappers.py`](/code/stable/tensorflow/python/keras/layers/wrappers.py).

<!-- Placeholder for "Used in" -->

Wrappers take another layer and augment it in various ways.
Do not use this class as a layer, it is only an abstract base class.
Two usable wrappers are the `TimeDistributed` and `Bidirectional` wrappers.

#### Arguments:


* <b>`layer`</b>: The layer to be wrapped.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    layer,
    **kwargs
)
```






