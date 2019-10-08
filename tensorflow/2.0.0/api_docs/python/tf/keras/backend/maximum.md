<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.maximum" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.maximum

``` python
tf.keras.backend.maximum(
    x,
    y
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Element-wise maximum of two tensors.

#### Arguments:

* <b>`x`</b>: Tensor or variable.
* <b>`y`</b>: Tensor or variable.


#### Returns:

    A tensor with the element wise maximum value(s) of `x` and `y`.

Examples:
```python
    # maximum of two tensors
    >>> x = tf.Variable([[1, 2], [3, 4]])
    >>> y = tf.Variable([[2, 1], [0, -1]])
    >>> m = tf.keras.backend.maximum(x, y)
    >>> m
    <tf.Tensor: id=42, shape=(2, 2), dtype=int32, numpy=
    array([[2, 2],
           [3, 4]], dtype=int32)>
```