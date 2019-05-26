<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.eye" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.eye

``` python
tf.keras.backend.eye(
    size,
    dtype=None,
    name=None
)
```



Defined in [`tensorflow/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/backend.py).

Instantiate an identity matrix and returns it.

#### Arguments:

* <b>`size`</b>: Integer, number of rows/columns.
* <b>`dtype`</b>: String, data type of returned Keras variable.
* <b>`name`</b>: String, name of returned Keras variable.


#### Returns:

    A Keras variable, an identity matrix.

Example:
```python
    >>> from keras import backend as K
    >>> kvar = K.eye(3)
    >>> K.eval(kvar)
    array([[ 1.,  0.,  0.],
           [ 0.,  1.,  0.],
           [ 0.,  0.,  1.]], dtype=float32)
```