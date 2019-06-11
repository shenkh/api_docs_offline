<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.batch_get_value" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.batch_get_value

Returns the value of more than one tensor variable.

### Aliases:

* `tf.compat.v1.keras.backend.batch_get_value`
* `tf.compat.v2.keras.backend.batch_get_value`
* `tf.keras.backend.batch_get_value`

``` python
tf.keras.backend.batch_get_value(tensors)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`tensors`</b>: list of ops to run.


#### Returns:

A list of Numpy arrays.



#### Raises:


* <b>`RuntimeError`</b>: If this method is called inside defun.