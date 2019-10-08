<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.repeat" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.repeat

``` python
tf.keras.backend.repeat(
    x,
    n
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Repeats a 2D tensor.

if `x` has shape (samples, dim) and `n` is `2`,
the output will have shape `(samples, 2, dim)`.

#### Arguments:

* <b>`x`</b>: Tensor or variable.
* <b>`n`</b>: Python integer, number of times to repeat.


#### Returns:

    A tensor.

Example:
    ```python
      >>> b = tf.constant([[1, 2], [3, 4]])
      >>> b
      <tf.Tensor: id=78, shape=(2, 2), dtype=int32, numpy=
      array([[1, 2],
             [3, 4]], dtype=int32)>
      >>> tf.keras.backend.repeat(b, n=2)
      <tf.Tensor: id=82, shape=(2, 2, 2), dtype=int32, numpy=
      array([[[1, 2],
              [1, 2]],
             [[3, 4],
              [3, 4]]], dtype=int32)>
    ```