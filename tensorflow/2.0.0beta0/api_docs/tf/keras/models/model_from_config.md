<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.models.model_from_config" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.models.model_from_config

Instantiates a Keras model from its config.

### Aliases:

* `tf.compat.v1.keras.models.model_from_config`
* `tf.compat.v2.keras.models.model_from_config`
* `tf.keras.models.model_from_config`

``` python
tf.keras.models.model_from_config(
    config,
    custom_objects=None
)
```



Defined in [`python/keras/saving/model_config.py`](/code/stable/tensorflow/python/keras/saving/model_config.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`config`</b>: Configuration dictionary.
* <b>`custom_objects`</b>: Optional dictionary mapping names
    (strings) to custom classes or functions to be
    considered during deserialization.


#### Returns:

A Keras model instance (uncompiled).



#### Raises:


* <b>`TypeError`</b>: if `config` is not a dictionary.