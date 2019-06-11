<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.activations.hard_sigmoid" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.activations.hard_sigmoid

Hard sigmoid activation function.

### Aliases:

* `tf.compat.v1.keras.activations.hard_sigmoid`
* `tf.compat.v2.keras.activations.hard_sigmoid`
* `tf.keras.activations.hard_sigmoid`

``` python
tf.keras.activations.hard_sigmoid(x)
```



Defined in [`python/keras/activations.py`](/code/stable/tensorflow/python/keras/activations.py).

<!-- Placeholder for "Used in" -->

Faster to compute than sigmoid activation.

#### Arguments:


* <b>`x`</b>: Input tensor.


#### Returns:

Hard sigmoid activation:
- `0` if `x < -2.5`
- `1` if `x > 2.5`
- `0.2 * x + 0.5` if `-2.5 <= x <= 2.5`.
