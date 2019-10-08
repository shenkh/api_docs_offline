<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.cumprod" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.cumprod

``` python
tf.keras.backend.cumprod(
    x,
    axis=0
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Cumulative product of the values in a tensor, alongside the specified axis.

#### Arguments:

* <b>`x`</b>: A tensor or variable.
* <b>`axis`</b>: An integer, the axis to compute the product.


#### Returns:

A tensor of the cumulative product of values of `x` along `axis`.