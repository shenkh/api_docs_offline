<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.experimental.function_executor_type" />
<meta itemprop="path" content="Stable" />
</div>

# tf.experimental.function_executor_type

``` python
tf.experimental.function_executor_type(executor_type)
```



Defined in [`tensorflow/python/eager/context.py`](/code/stable/tensorflow/python/eager/context.py).

Context manager for setting the executor of eager defined functions.

Eager defined functions are functions decorated by tf.contrib.eager.defun.

#### Args:

* <b>`executor_type`</b>: a string for the name of the executor to be used to execute
    functions defined by tf.contrib.eager.defun.


#### Yields:

Context manager for setting the executor of eager defined functions.