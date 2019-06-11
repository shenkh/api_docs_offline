<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.floatx" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.floatx

Returns the default float type, as a string.

### Aliases:

* `tf.compat.v1.keras.backend.floatx`
* `tf.compat.v2.keras.backend.floatx`
* `tf.keras.backend.floatx`

``` python
tf.keras.backend.floatx()
```



Defined in [`python/keras/backend_config.py`](/code/stable/tensorflow/python/keras/backend_config.py).

<!-- Placeholder for "Used in" -->

E.g. 'float16', 'float32', 'float64'.

#### Returns:

String, the current default float type.



#### Example:


```python
keras.backend.floatx() >>> 'float32'
```