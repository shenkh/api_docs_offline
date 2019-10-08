<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.stack" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.stack

``` python
tf.keras.backend.stack(
    x,
    axis=0
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Stacks a list of rank `R` tensors into a rank `R+1` tensor.

#### Arguments:

* <b>`x`</b>: List of tensors.
* <b>`axis`</b>: Axis along which to perform stacking.


#### Returns:

    A tensor.

Example:
    ```python
      >>> a = tf.constant([[1, 2],[3, 4]])
      >>> b = tf.constant([[10, 20],[30, 40]])
      >>> tf.keras.backend.stack((a, b))
      <tf.Tensor: id=146, shape=(2, 2, 2), dtype=int32, numpy=
      array([[[ 1,  2],
              [ 3,  4]],
             [[10, 20],
              [30, 40]]], dtype=int32)>
    ```