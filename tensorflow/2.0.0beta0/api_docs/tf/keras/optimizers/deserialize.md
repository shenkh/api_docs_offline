<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.optimizers.deserialize" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.optimizers.deserialize

Inverse of the `serialize` function.

### Aliases:

* `tf.compat.v1.keras.optimizers.deserialize`
* `tf.compat.v2.keras.optimizers.deserialize`
* `tf.compat.v2.optimizers.deserialize`
* `tf.keras.optimizers.deserialize`
* `tf.optimizers.deserialize`

``` python
tf.keras.optimizers.deserialize(
    config,
    custom_objects=None
)
```



Defined in [`python/keras/optimizers.py`](/code/stable/tensorflow/python/keras/optimizers.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`config`</b>: Optimizer configuration dictionary.
* <b>`custom_objects`</b>: Optional dictionary mapping names (strings) to custom
  objects (classes and functions) to be considered during deserialization.


#### Returns:

A Keras Optimizer instance.
