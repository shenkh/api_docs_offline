<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.experimental.function_executor_type" />
<meta itemprop="path" content="Stable" />
</div>

# tf.experimental.function_executor_type

Context manager for setting the executor of eager defined functions.

### Aliases:

* `tf.compat.v1.experimental.function_executor_type`
* `tf.compat.v2.experimental.function_executor_type`
* `tf.experimental.function_executor_type`

``` python
tf.experimental.function_executor_type(executor_type)
```



Defined in [`python/eager/context.py`](/code/stable/tensorflow/python/eager/context.py).

<!-- Placeholder for "Used in" -->

Eager defined functions are functions decorated by tf.contrib.eager.defun.

#### Args:


* <b>`executor_type`</b>: a string for the name of the executor to be used to execute
  functions defined by tf.contrib.eager.defun.


#### Yields:

Context manager for setting the executor of eager defined functions.
