<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.count_params" />
</div>

# tf.keras.backend.count_params

``` python
tf.keras.backend.count_params(x)
```



Defined in [`tensorflow/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/backend.py).

Returns the static number of elements in a variable or tensor.

#### Arguments:

* <b>`x`</b>: Variable or tensor.


#### Returns:

    Integer, the number of scalars in `x`.

Example:
```python
    >>> kvar = K.zeros((2,3))
    >>> K.count_params(kvar)
    6
    >>> K.eval(kvar)
    array([[ 0.,  0.,  0.],
           [ 0.,  0.,  0.]], dtype=float32)
```