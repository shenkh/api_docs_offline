<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.concatenate" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.concatenate

``` python
tf.keras.backend.concatenate(
    tensors,
    axis=-1
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Concatenates a list of tensors alongside the specified axis.

#### Arguments:

* <b>`tensors`</b>: list of tensors to concatenate.
* <b>`axis`</b>: concatenation axis.


#### Returns:

    A tensor.

Example:
    ```python
    >>> a = tf.constant([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
    >>> b = tf.constant([[10, 20, 30], [40, 50, 60], [70, 80, 90]])
    >>> tf.keras.backend.concatenate((a, b), axis=-1)
    <tf.Tensor: id=14, shape=(3, 6), dtype=int32, numpy=
    array([[ 1,  2,  3, 10, 20, 30],
           [ 4,  5,  6, 40, 50, 60],
           [ 7,  8,  9, 70, 80, 90]], dtype=int32)>
    ```