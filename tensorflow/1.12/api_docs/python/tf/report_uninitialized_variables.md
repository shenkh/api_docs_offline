<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.report_uninitialized_variables" />
<meta itemprop="path" content="Stable" />
</div>

# tf.report_uninitialized_variables

``` python
tf.report_uninitialized_variables(
    var_list=None,
    name='report_uninitialized_variables'
)
```



Defined in [`tensorflow/python/ops/variables.py`](/code/stable/tensorflow/python/ops/variables.py).

Adds ops to list the names of uninitialized variables.

When run, it returns a 1-D tensor containing the names of uninitialized
variables if there are any, or an empty array if there are none.

#### Args:

* <b>`var_list`</b>: List of `Variable` objects to check. Defaults to the
    value of `global_variables() + local_variables()`
* <b>`name`</b>: Optional name of the `Operation`.


#### Returns:

  A 1-D tensor containing names of the uninitialized variables, or an empty
  1-D tensor if there are no variables or no uninitialized variables.


**NOTE** The output of this function should be used.  If it is not, a warning will be logged.  To mark the output as used, call its .mark_used() method.