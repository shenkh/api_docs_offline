<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.set_floatx" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.set_floatx

``` python
tf.keras.backend.set_floatx(value)
```



Defined in [`tensorflow/python/keras/backend_config.py`](/code/stable/tensorflow/python/keras/backend_config.py).

Sets the default float type.

#### Arguments:

* <b>`value`</b>: String; 'float16', 'float32', or 'float64'.
Example: ```python from keras import backend as K K.floatx() >>> 'float32'
  K.set_floatx('float16') K.floatx() >>> 'float16' ```


#### Raises:

* <b>`ValueError`</b>: In case of invalid value.