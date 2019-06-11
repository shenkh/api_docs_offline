<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.is_sparse" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.is_sparse

Returns whether a tensor is a sparse tensor.

### Aliases:

* `tf.compat.v1.keras.backend.is_sparse`
* `tf.compat.v2.keras.backend.is_sparse`
* `tf.keras.backend.is_sparse`

``` python
tf.keras.backend.is_sparse(tensor)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`tensor`</b>: A tensor instance.


#### Returns:

A boolean.



#### Example:


```python
    >>> from keras import backend as K
    >>> a = K.placeholder((2, 2), sparse=False)
    >>> print(K.is_sparse(a))
    False
    >>> b = K.placeholder((2, 2), sparse=True)
    >>> print(K.is_sparse(b))
    True
```