<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.permute_dimensions" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.permute_dimensions

``` python
tf.keras.backend.permute_dimensions(
    x,
    pattern
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Permutes axes in a tensor.

#### Arguments:

* <b>`x`</b>: Tensor or variable.
* <b>`pattern`</b>: A tuple of
        dimension indices, e.g. `(0, 2, 1)`.


#### Returns:

    A tensor.

Example:
  ```python
    >>> a = tf.constant([[1, 2, 3], [4, 5, 6], [7, 8, 9], [10, 11, 12]])
    >>> a
    <tf.Tensor: id=49, shape=(4, 3), dtype=int32, numpy=
    array([[ 1,  2,  3],
           [ 4,  5,  6],
           [ 7,  8,  9],
           [10, 11, 12]], dtype=int32)>
    >>> tf.keras.backend.permute_dimensions(a, pattern=(1, 0))
    <tf.Tensor: id=52, shape=(3, 4), dtype=int32, numpy=
    array([[ 1,  4,  7, 10],
           [ 2,  5,  8, 11],
           [ 3,  6,  9, 12]], dtype=int32)>
  ```