<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.optimizers.deserialize" />
</div>

# tf.keras.optimizers.deserialize

``` python
tf.keras.optimizers.deserialize(
    config,
    custom_objects=None
)
```



Defined in [`tensorflow/python/keras/optimizers.py`](https://www.tensorflow.org/code/tensorflow/python/keras/optimizers.py).

Inverse of the `serialize` function.

#### Arguments:

* <b>`config`</b>: Optimizer configuration dictionary.
* <b>`custom_objects`</b>: Optional dictionary mapping
        names (strings) to custom objects
        (classes and functions)
        to be considered during deserialization.


#### Returns:

A Keras Optimizer instance.