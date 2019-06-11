<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.UpSampling1D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.UpSampling1D

## Class `UpSampling1D`

Upsampling layer for 1D inputs.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

### Aliases:

* Class `tf.compat.v1.keras.layers.UpSampling1D`
* Class `tf.compat.v2.keras.layers.UpSampling1D`
* Class `tf.keras.layers.UpSampling1D`



Defined in [`python/keras/layers/convolutional.py`](/code/stable/tensorflow/python/keras/layers/convolutional.py).

<!-- Placeholder for "Used in" -->

Repeats each temporal step `size` times along the time axis.

#### Arguments:


* <b>`size`</b>: Integer. Upsampling factor.


#### Input shape:

3D tensor with shape: `(batch, steps, features)`.



#### Output shape:

3D tensor with shape: `(batch, upsampled_steps, features)`.


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    size=2,
    **kwargs
)
```






