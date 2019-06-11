<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.cast_to_floatx" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.cast_to_floatx

Cast a Numpy array to the default Keras float type.

### Aliases:

* `tf.compat.v1.keras.backend.cast_to_floatx`
* `tf.compat.v2.keras.backend.cast_to_floatx`
* `tf.keras.backend.cast_to_floatx`

``` python
tf.keras.backend.cast_to_floatx(x)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Numpy array.


#### Returns:

The same Numpy array, cast to its new type.



#### Example:


```python
    >>> from keras import backend as K
    >>> K.floatx()
    'float32'
    >>> arr = numpy.array([1.0, 2.0], dtype='float64')
    >>> arr.dtype
    dtype('float64')
    >>> new_arr = K.cast_to_floatx(arr)
    >>> new_arr
    array([ 1.,  2.], dtype=float32)
    >>> new_arr.dtype
    dtype('float32')
```