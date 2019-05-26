<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.models.model_from_yaml" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.models.model_from_yaml

``` python
tf.keras.models.model_from_yaml(
    yaml_string,
    custom_objects=None
)
```



Defined in [`tensorflow/python/keras/engine/saving.py`](/code/stable/tensorflow/python/keras/engine/saving.py).

Parses a yaml model configuration file and returns a model instance.

#### Arguments:

* <b>`yaml_string`</b>: YAML string encoding a model configuration.
* <b>`custom_objects`</b>: Optional dictionary mapping names
        (strings) to custom classes or functions to be
        considered during deserialization.


#### Returns:

A Keras model instance (uncompiled).


#### Raises:

* <b>`ImportError`</b>: if yaml module is not found.