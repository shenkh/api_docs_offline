<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.max" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.max

Maximum value in a tensor.

### Aliases:

* `tf.compat.v1.keras.backend.max`
* `tf.compat.v2.keras.backend.max`
* `tf.keras.backend.max`

``` python
tf.keras.backend.max(
    x,
    axis=None,
    keepdims=False
)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: A tensor or variable.
* <b>`axis`</b>: An integer, the axis to find maximum values.
* <b>`keepdims`</b>: A boolean, whether to keep the dimensions or not.
    If `keepdims` is `False`, the rank of the tensor is reduced
    by 1. If `keepdims` is `True`,
    the reduced dimension is retained with length 1.


#### Returns:

A tensor with maximum values of `x`.
