<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.ones" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.ones

``` python
tf.keras.backend.ones(
    shape,
    dtype=None,
    name=None
)
```



Defined in [`tensorflow/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/backend.py).

Instantiates an all-ones variable and returns it.

#### Arguments:

* <b>`shape`</b>: Tuple of integers, shape of returned Keras variable.
* <b>`dtype`</b>: String, data type of returned Keras variable.
* <b>`name`</b>: String, name of returned Keras variable.


#### Returns:

    A Keras variable, filled with `1.0`.
    Note that if `shape` was symbolic, we cannot return a variable,
    and will return a dynamically-shaped tensor instead.

Example:
```python
    >>> from keras import backend as K
    >>> kvar = K.ones((3,4))
    >>> K.eval(kvar)
    array([[ 1.,  1.,  1.,  1.],
           [ 1.,  1.,  1.,  1.],
           [ 1.,  1.,  1.,  1.]], dtype=float32)
```