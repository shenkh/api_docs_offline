<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.dropout" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.dropout

Sets entries in `x` to zero at random, while scaling the entire tensor.

### Aliases:

* `tf.compat.v1.keras.backend.dropout`
* `tf.compat.v2.keras.backend.dropout`
* `tf.keras.backend.dropout`

``` python
tf.keras.backend.dropout(
    x,
    level,
    noise_shape=None,
    seed=None
)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: tensor
* <b>`level`</b>: fraction of the entries in the tensor
    that will be set to 0.
* <b>`noise_shape`</b>: shape for randomly generated keep/drop flags,
    must be broadcastable to the shape of `x`
* <b>`seed`</b>: random seed to ensure determinism.


#### Returns:

A tensor.
