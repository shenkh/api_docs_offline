<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.arg_scoped_arguments" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.framework.arg_scoped_arguments

``` python
tf.contrib.framework.arg_scoped_arguments(func)
```



Defined in [`tensorflow/contrib/framework/python/ops/arg_scope.py`](/code/stable/tensorflow/contrib/framework/python/ops/arg_scope.py).

Returns the list kwargs that arg_scope can set for a func.

#### Args:

* <b>`func`</b>: function which has been decorated with @add_arg_scope.


#### Returns:

a list of kwargs names.