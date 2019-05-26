<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.min" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.min

``` python
tf.keras.backend.min(
    x,
    axis=None,
    keepdims=False
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Minimum value in a tensor.

#### Arguments:

* <b>`x`</b>: A tensor or variable.
* <b>`axis`</b>: An integer, the axis to find minimum values.
* <b>`keepdims`</b>: A boolean, whether to keep the dimensions or not.
        If `keepdims` is `False`, the rank of the tensor is reduced
        by 1. If `keepdims` is `True`,
        the reduced dimension is retained with length 1.


#### Returns:

A tensor with miminum values of `x`.