<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.zeros" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.zeros

Instantiates an all-zeros variable and returns it.

### Aliases:

* `tf.compat.v1.keras.backend.zeros`
* `tf.compat.v2.keras.backend.zeros`
* `tf.keras.backend.zeros`

``` python
tf.keras.backend.zeros(
    shape,
    dtype=None,
    name=None
)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`shape`</b>: Tuple of integers, shape of returned Keras variable
* <b>`dtype`</b>: String, data type of returned Keras variable
* <b>`name`</b>: String, name of returned Keras variable


#### Returns:

A variable (including Keras metadata), filled with `0.0`.
Note that if `shape` was symbolic, we cannot return a variable,
and will return a dynamically-shaped tensor instead.



#### Example:


```python
    >>> from keras import backend as K
    >>> kvar = K.zeros((3,4))
    >>> K.eval(kvar)
    array([[ 0.,  0.,  0.,  0.],
           [ 0.,  0.,  0.,  0.],
           [ 0.,  0.,  0.,  0.]], dtype=float32)
```