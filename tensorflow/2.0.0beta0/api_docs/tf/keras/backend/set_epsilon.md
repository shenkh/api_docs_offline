<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.set_epsilon" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.set_epsilon

Sets the value of the fuzz factor used in numeric expressions.

### Aliases:

* `tf.compat.v1.keras.backend.set_epsilon`
* `tf.compat.v2.keras.backend.set_epsilon`
* `tf.keras.backend.set_epsilon`

``` python
tf.keras.backend.set_epsilon(value)
```



Defined in [`python/keras/backend_config.py`](/code/stable/tensorflow/python/keras/backend_config.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`value`</b>: float. New value of epsilon.
Example: ```python from keras import backend as K K.epsilon() >>> 1e-07
  K.set_epsilon(1e-05) K.epsilon() >>> 1e-05 ```