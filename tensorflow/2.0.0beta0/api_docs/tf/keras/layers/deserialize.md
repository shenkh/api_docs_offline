<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.deserialize" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.layers.deserialize

Instantiates a layer from a config dictionary.

### Aliases:

* `tf.compat.v1.keras.layers.deserialize`
* `tf.compat.v2.keras.layers.deserialize`
* `tf.keras.layers.deserialize`

``` python
tf.keras.layers.deserialize(
    config,
    custom_objects=None
)
```



Defined in [`python/keras/layers/serialization.py`](/code/stable/tensorflow/python/keras/layers/serialization.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`config`</b>: dict of the form {'class_name': str, 'config': dict}
* <b>`custom_objects`</b>: dict mapping class names (or function names)
    of custom (non-Keras) objects to class/functions


#### Returns:

Layer instance (may be Model, Sequential, Network, Layer...)
