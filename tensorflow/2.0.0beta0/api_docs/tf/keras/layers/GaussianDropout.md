<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.GaussianDropout" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.GaussianDropout

## Class `GaussianDropout`

Apply multiplicative 1-centered Gaussian noise.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

### Aliases:

* Class `tf.compat.v1.keras.layers.GaussianDropout`
* Class `tf.compat.v2.keras.layers.GaussianDropout`
* Class `tf.keras.layers.GaussianDropout`



Defined in [`python/keras/layers/noise.py`](/code/stable/tensorflow/python/keras/layers/noise.py).

<!-- Placeholder for "Used in" -->

As it is a regularization layer, it is only active at training time.

#### Arguments:


* <b>`rate`</b>: Float, drop probability (as with `Dropout`).
  The multiplicative noise will have
  standard deviation `sqrt(rate / (1 - rate))`.


#### Call arguments:


* <b>`inputs`</b>: Input tensor (of any rank).
* <b>`training`</b>: Python boolean indicating whether the layer should behave in
  training mode (adding dropout) or in inference mode (doing nothing).


#### Input shape:

Arbitrary. Use the keyword argument `input_shape`
(tuple of integers, does not include the samples axis)
when using this layer as the first layer in a model.



#### Output shape:

Same shape as input.


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    rate,
    **kwargs
)
```






