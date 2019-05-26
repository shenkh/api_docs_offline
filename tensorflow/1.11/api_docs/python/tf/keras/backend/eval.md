<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.eval" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.eval

``` python
tf.keras.backend.eval(x)
```



Defined in [`tensorflow/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/backend.py).

Evaluates the value of a variable.

#### Arguments:

* <b>`x`</b>: A variable.


#### Returns:

    A Numpy array.

Examples:
```python
    >>> from keras import backend as K
    >>> kvar = K.variable(np.array([[1, 2], [3, 4]]), dtype='float32')
    >>> K.eval(kvar)
    array([[ 1.,  2.],
           [ 3.,  4.]], dtype=float32)
```