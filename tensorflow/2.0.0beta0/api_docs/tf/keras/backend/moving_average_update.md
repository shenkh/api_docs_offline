<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.moving_average_update" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.moving_average_update

Compute the moving average of a variable.

### Aliases:

* `tf.compat.v1.keras.backend.moving_average_update`
* `tf.compat.v2.keras.backend.moving_average_update`
* `tf.keras.backend.moving_average_update`

``` python
tf.keras.backend.moving_average_update(
    x,
    value,
    momentum
)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: A Variable.
* <b>`value`</b>: A tensor with the same shape as `variable`.
* <b>`momentum`</b>: The moving average momentum.


#### Returns:

An Operation to update the variable.
