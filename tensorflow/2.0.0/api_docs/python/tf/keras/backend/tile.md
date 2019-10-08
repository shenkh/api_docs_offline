<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.tile" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.tile

``` python
tf.keras.backend.tile(
    x,
    n
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Creates a tensor by tiling `x` by `n`.

#### Arguments:

* <b>`x`</b>: A tensor or variable
* <b>`n`</b>: A list of integer. The length must be the same as the number of
        dimensions in `x`.


#### Returns:

A tiled tensor.