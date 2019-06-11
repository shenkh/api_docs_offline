<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.count_params" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.count_params

Returns the static number of elements in a variable or tensor.

### Aliases:

* `tf.compat.v1.keras.backend.count_params`
* `tf.compat.v2.keras.backend.count_params`
* `tf.keras.backend.count_params`

``` python
tf.keras.backend.count_params(x)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Variable or tensor.


#### Returns:

Integer, the number of scalars in `x`.



#### Example:


```python
    >>> kvar = K.zeros((2,3))
    >>> K.count_params(kvar)
    6
    >>> K.eval(kvar)
    array([[ 0.,  0.,  0.],
           [ 0.,  0.,  0.]], dtype=float32)
```