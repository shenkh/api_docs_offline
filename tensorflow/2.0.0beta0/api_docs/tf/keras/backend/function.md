<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.function" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.function

Instantiates a Keras function.

### Aliases:

* `tf.compat.v1.keras.backend.function`
* `tf.compat.v2.keras.backend.function`
* `tf.keras.backend.function`

``` python
tf.keras.backend.function(
    inputs,
    outputs,
    updates=None,
    name=None,
    **kwargs
)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`inputs`</b>: List of placeholder tensors.
* <b>`outputs`</b>: List of output tensors.
* <b>`updates`</b>: List of update ops.
* <b>`name`</b>: String, name of function.
* <b>`**kwargs`</b>: Passed to `tf.Session.run`.


#### Returns:

Output values as Numpy arrays.



#### Raises:


* <b>`ValueError`</b>: if invalid kwargs are passed in or if in eager execution.