<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.function" />
</div>

# tf.keras.backend.function

``` python
tf.keras.backend.function(
    inputs,
    outputs,
    updates=None,
    **kwargs
)
```



Defined in [`tensorflow/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/backend.py).

Instantiates a Keras function.

#### Arguments:

* <b>`inputs`</b>: List of placeholder tensors.
* <b>`outputs`</b>: List of output tensors.
* <b>`updates`</b>: List of update ops.
* <b>`**kwargs`</b>: Passed to <a href="../../../tf/InteractiveSession.md#run"><code>tf.Session.run</code></a>.


#### Returns:

Output values as Numpy arrays.


#### Raises:

* <b>`ValueError`</b>: if invalid kwargs are passed in.