<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.squeeze" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.squeeze

Removes a 1-dimension from the tensor at index "axis".

### Aliases:

* `tf.compat.v1.keras.backend.squeeze`
* `tf.compat.v2.keras.backend.squeeze`
* `tf.keras.backend.squeeze`

``` python
tf.keras.backend.squeeze(
    x,
    axis
)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: A tensor or variable.
* <b>`axis`</b>: Axis to drop.


#### Returns:

A tensor with the same data as `x` but reduced dimensions.
