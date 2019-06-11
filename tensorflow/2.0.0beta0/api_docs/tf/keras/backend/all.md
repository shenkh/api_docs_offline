<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.all" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.all

Bitwise reduction (logical AND).

### Aliases:

* `tf.compat.v1.keras.backend.all`
* `tf.compat.v2.keras.backend.all`
* `tf.keras.backend.all`

``` python
tf.keras.backend.all(
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
