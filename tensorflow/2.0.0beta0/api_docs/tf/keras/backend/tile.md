<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.tile" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.tile

Creates a tensor by tiling `x` by `n`.

### Aliases:

* `tf.compat.v1.keras.backend.tile`
* `tf.compat.v2.keras.backend.tile`
* `tf.keras.backend.tile`

``` python
tf.keras.backend.tile(
    x,
    n
)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: A tensor or variable
* <b>`n`</b>: A list of integer. The length must be the same as the number of
    dimensions in `x`.


#### Returns:

A tiled tensor.
