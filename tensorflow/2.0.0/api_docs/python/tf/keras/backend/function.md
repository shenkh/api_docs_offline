<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.function" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.function

``` python
tf.keras.backend.function(
    inputs,
    outputs,
    updates=None,
    name=None,
    **kwargs
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Instantiates a Keras function.

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