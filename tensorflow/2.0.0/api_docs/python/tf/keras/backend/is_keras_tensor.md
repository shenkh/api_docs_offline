<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.is_keras_tensor" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.is_keras_tensor

``` python
tf.keras.backend.is_keras_tensor(x)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Returns whether `x` is a Keras tensor.

A "Keras tensor" is a tensor that was returned by a Keras layer,
(`Layer` class) or by `Input`.

#### Arguments:

* <b>`x`</b>: A candidate tensor.


#### Returns:

A boolean: Whether the argument is a Keras tensor.


#### Raises:

* <b>`ValueError`</b>: In case `x` is not a symbolic tensor.

Examples:
```python
    >>> import tensorflow as tf
    >>> import numpy
    >>> from keras import backend as K
    >>> from keras.layers import Input, Dense
    >>> np_var = numpy.array([1, 2])
    >>> K.is_keras_tensor(np_var) # A numpy array is not a symbolic tensor.
    ValueError
    >>> k_var = tf.compat.v1.placeholder('float32', shape=(1,1))
    >>> K.is_keras_tensor(k_var) # A variable indirectly created outside of
    keras is not a Keras tensor.
    False
    >>> keras_var = K.variable(np_var)
    >>> K.is_keras_tensor(keras_var)  # A variable created with the keras
    backend is not a Keras tensor.
    False
    >>> keras_placeholder = K.placeholder(shape=(2, 4, 5))
    >>> K.is_keras_tensor(keras_placeholder)  # A placeholder is not a Keras
    tensor.
    False
    >>> keras_input = Input([10])
    >>> K.is_keras_tensor(keras_input) # An Input is a Keras tensor.
    True
    >>> keras_layer_output = Dense(10)(keras_input)
    >>> K.is_keras_tensor(keras_layer_output) # Any Keras layer output is a
    Keras tensor.
    True
```