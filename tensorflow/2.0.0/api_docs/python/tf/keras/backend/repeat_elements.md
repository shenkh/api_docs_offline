<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.repeat_elements" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.repeat_elements

``` python
tf.keras.backend.repeat_elements(
    x,
    rep,
    axis
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Repeats the elements of a tensor along an axis, like `np.repeat`.

If `x` has shape `(s1, s2, s3)` and `axis` is `1`, the output
will have shape `(s1, s2 * rep, s3)`.

#### Arguments:

* <b>`x`</b>: Tensor or variable.
* <b>`rep`</b>: Python integer, number of times to repeat.
* <b>`axis`</b>: Axis along which to repeat.


#### Returns:

    A tensor.

Example:
    ```python
      >>> b = tf.constant([1, 2, 3])
      >>> tf.keras.backend.repeat_elements(b, rep=2, axis=0)
      <tf.Tensor: id=70, shape=(6,), dtype=int32,
          numpy=array([1, 1, 2, 2, 3, 3], dtype=int32)>
    ```