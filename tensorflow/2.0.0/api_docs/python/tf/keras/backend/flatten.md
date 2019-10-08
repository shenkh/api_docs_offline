<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.flatten" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.flatten

``` python
tf.keras.backend.flatten(x)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Flatten a tensor.

#### Arguments:

* <b>`x`</b>: A tensor or variable.


#### Returns:

    A tensor, reshaped into 1-D

Example:
    ```python
      >>> b = tf.constant([[1, 2], [3, 4]])
      >>> b
      <tf.Tensor: id=102, shape=(2, 2), dtype=int32, numpy=
      array([[1, 2],
             [3, 4]], dtype=int32)>
      >>> tf.keras.backend.flatten(b)
      <tf.Tensor: id=105, shape=(4,), dtype=int32,
          numpy=array([1, 2, 3, 4], dtype=int32)>
    ```