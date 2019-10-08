<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.optimizers.get" />
<meta itemprop="path" content="Stable" />
</div>

# tf.optimizers.get

### Aliases:

* `tf.keras.optimizers.get`
* `tf.optimizers.get`

``` python
tf.optimizers.get(identifier)
```



Defined in [`tensorflow/python/keras/optimizers.py`](/code/stable/tensorflow/python/keras/optimizers.py).

Retrieves a Keras Optimizer instance.

#### Arguments:

* <b>`identifier`</b>: Optimizer identifier, one of
        - String: name of an optimizer
        - Dictionary: configuration dictionary. - Keras Optimizer instance (it
          will be returned unchanged). - TensorFlow Optimizer instance (it
          will be wrapped as a Keras Optimizer).


#### Returns:

A Keras Optimizer instance.


#### Raises:

* <b>`ValueError`</b>: If `identifier` cannot be interpreted.