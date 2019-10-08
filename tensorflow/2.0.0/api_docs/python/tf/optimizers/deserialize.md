<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.optimizers.deserialize" />
<meta itemprop="path" content="Stable" />
</div>

# tf.optimizers.deserialize

### Aliases:

* `tf.keras.optimizers.deserialize`
* `tf.optimizers.deserialize`

``` python
tf.optimizers.deserialize(
    config,
    custom_objects=None
)
```



Defined in [`tensorflow/python/keras/optimizers.py`](/code/stable/tensorflow/python/keras/optimizers.py).

Inverse of the `serialize` function.

#### Arguments:

* <b>`config`</b>: Optimizer configuration dictionary.
* <b>`custom_objects`</b>: Optional dictionary mapping names (strings) to custom
      objects (classes and functions) to be considered during deserialization.


#### Returns:

A Keras Optimizer instance.