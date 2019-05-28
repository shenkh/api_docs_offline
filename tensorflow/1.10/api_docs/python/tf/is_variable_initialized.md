<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.is_variable_initialized" />
</div>

# tf.is_variable_initialized

``` python
tf.is_variable_initialized(variable)
```



Defined in [`tensorflow/python/ops/variables.py`](https://www.tensorflow.org/code/tensorflow/python/ops/variables.py).

See the guide: [Variables > Variable helper functions](../../../api_guides/python/state_ops.md#Variable_helper_functions)

Tests if a variable has been initialized.

#### Args:

* <b>`variable`</b>: A `Variable`.


#### Returns:

  Returns a scalar boolean Tensor, `True` if the variable has been
  initialized, `False` otherwise.


**NOTE** The output of this function should be used.  If it is not, a warning will be logged.  To mark the output as used, call its .mark_used() method.