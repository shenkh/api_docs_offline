<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.models.model_from_yaml" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.models.model_from_yaml

Parses a yaml model configuration file and returns a model instance.

### Aliases:

* `tf.compat.v1.keras.models.model_from_yaml`
* `tf.compat.v2.keras.models.model_from_yaml`
* `tf.keras.models.model_from_yaml`

``` python
tf.keras.models.model_from_yaml(
    yaml_string,
    custom_objects=None
)
```



Defined in [`python/keras/saving/model_config.py`](/code/stable/tensorflow/python/keras/saving/model_config.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`yaml_string`</b>: YAML string encoding a model configuration.
* <b>`custom_objects`</b>: Optional dictionary mapping names
    (strings) to custom classes or functions to be
    considered during deserialization.


#### Returns:

A Keras model instance (uncompiled).



#### Raises:


* <b>`ImportError`</b>: if yaml module is not found.