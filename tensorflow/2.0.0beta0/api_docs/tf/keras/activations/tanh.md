<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.activations.tanh" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.activations.tanh

Hyperbolic Tangent activation function.

### Aliases:

* `tf.compat.v1.keras.activations.tanh`
* `tf.compat.v2.keras.activations.tanh`
* `tf.keras.activations.tanh`

``` python
tf.keras.activations.tanh(x)
```



Defined in [`python/keras/activations.py`](/code/stable/tensorflow/python/keras/activations.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Input tensor.


#### Returns:

The tanh activation: `tanh(x) = sinh(x)/cosh(x) = ((exp(x) -
exp(-x))/(exp(x) + exp(-x)))`.
