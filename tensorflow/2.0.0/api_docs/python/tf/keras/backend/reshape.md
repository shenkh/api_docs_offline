<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.reshape" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.reshape

``` python
tf.keras.backend.reshape(
    x,
    shape
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Reshapes a tensor to the specified shape.

#### Arguments:

* <b>`x`</b>: Tensor or variable.
* <b>`shape`</b>: Target shape tuple.


#### Returns:

    A tensor.

Example:
  ```python
    >>> a = tf.constant([[1, 2, 3], [4, 5, 6], [7, 8, 9], [10, 11, 12]])
    >>> a
    <tf.Tensor: id=32, shape=(4, 3), dtype=int32, numpy=
    array([[ 1,  2,  3],
           [ 4,  5,  6],
           [ 7,  8,  9],
           [10, 11, 12]], dtype=int32)>
    >>> tf.keras.backend.reshape(a, shape=(2, 6))
    <tf.Tensor: id=35, shape=(2, 6), dtype=int32, numpy=
    array([[ 1,  2,  3,  4,  5,  6],
           [ 7,  8,  9, 10, 11, 12]], dtype=int32)>
  ```