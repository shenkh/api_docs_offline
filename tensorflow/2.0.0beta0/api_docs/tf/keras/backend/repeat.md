<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.repeat" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.repeat

Repeats a 2D tensor.

### Aliases:

* `tf.compat.v1.keras.backend.repeat`
* `tf.compat.v2.keras.backend.repeat`
* `tf.keras.backend.repeat`

``` python
tf.keras.backend.repeat(
    x,
    n
)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->

if `x` has shape (samples, dim) and `n` is `2`,
the output will have shape `(samples, 2, dim)`.

#### Arguments:


* <b>`x`</b>: Tensor or variable.
* <b>`n`</b>: Python integer, number of times to repeat.


#### Returns:

A tensor.
