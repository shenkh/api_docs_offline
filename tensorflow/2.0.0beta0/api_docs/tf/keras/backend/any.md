<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.any" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.any

Bitwise reduction (logical OR).

### Aliases:

* `tf.compat.v1.keras.backend.any`
* `tf.compat.v2.keras.backend.any`
* `tf.keras.backend.any`

``` python
tf.keras.backend.any(
    x,
    axis=None,
    keepdims=False
)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Tensor or variable.
* <b>`axis`</b>: axis along which to perform the reduction.
* <b>`keepdims`</b>: whether the drop or broadcast the reduction axes.


#### Returns:

A uint8 tensor (0s and 1s).
