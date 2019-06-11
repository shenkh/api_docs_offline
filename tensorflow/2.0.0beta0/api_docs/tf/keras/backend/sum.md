<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.sum" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.sum

Sum of the values in a tensor, alongside the specified axis.

### Aliases:

* `tf.compat.v1.keras.backend.sum`
* `tf.compat.v2.keras.backend.sum`
* `tf.keras.backend.sum`

``` python
tf.keras.backend.sum(
    x,
    axis=None,
    keepdims=False
)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: A tensor or variable.
* <b>`axis`</b>: An integer, the axis to sum over.
* <b>`keepdims`</b>: A boolean, whether to keep the dimensions or not.
    If `keepdims` is `False`, the rank of the tensor is reduced
    by 1. If `keepdims` is `True`,
    the reduced dimension is retained with length 1.


#### Returns:

A tensor with sum of `x`.
