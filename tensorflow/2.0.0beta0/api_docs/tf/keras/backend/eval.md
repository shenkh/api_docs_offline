<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.eval" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.eval

Evaluates the value of a variable.

### Aliases:

* `tf.compat.v1.keras.backend.eval`
* `tf.compat.v2.keras.backend.eval`
* `tf.keras.backend.eval`

``` python
tf.keras.backend.eval(x)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: A variable.


#### Returns:

A Numpy array.



#### Examples:


```python
    >>> from keras import backend as K
    >>> kvar = K.variable(np.array([[1, 2], [3, 4]]), dtype='float32')
    >>> K.eval(kvar)
    array([[ 1.,  2.],
           [ 3.,  4.]], dtype=float32)
```