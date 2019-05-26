<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.add_arg_scope" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.framework.add_arg_scope

``` python
tf.contrib.framework.add_arg_scope(func)
```



Defined in [`tensorflow/contrib/framework/python/ops/arg_scope.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/python/ops/arg_scope.py).

Decorates a function with args so it can be used within an arg_scope.

#### Args:

* <b>`func`</b>: function to decorate.


#### Returns:

A tuple with the decorated function func_with_args().