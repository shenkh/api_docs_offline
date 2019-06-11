<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.batch_flatten" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.batch_flatten

Turn a nD tensor into a 2D tensor with same 0th dimension.

### Aliases:

* `tf.compat.v1.keras.backend.batch_flatten`
* `tf.compat.v2.keras.backend.batch_flatten`
* `tf.keras.backend.batch_flatten`

``` python
tf.keras.backend.batch_flatten(x)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->

In other words, it flattens each data samples of a batch.

#### Arguments:


* <b>`x`</b>: A tensor or variable.


#### Returns:

A tensor.



#### Examples:

Flattening a 3D tensor to 2D by collapsing the last dimension.


```python
    >>> from tensorflow.keras import backend as K
    >>> x_batch = K.ones(shape=(2, 3, 4, 5))
    >>> x_batch_flatten = K.batch_flatten(x_batch)
    >>> K.int_shape(x_batch_flatten)
    (2, 60)
```