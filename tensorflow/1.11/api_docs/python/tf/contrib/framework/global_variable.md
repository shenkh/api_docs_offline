<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.global_variable" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.framework.global_variable

``` python
tf.contrib.framework.global_variable(
    initial_value,
    validate_shape=True,
    name=None,
    use_resource=None
)
```



Defined in [`tensorflow/contrib/framework/python/ops/variables.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/python/ops/variables.py).

Create a variable with a value and add it to `GraphKeys.GLOBAL_VARIABLES`.

#### Args:

* <b>`initial_value`</b>: See variables.Variable.__init__.
* <b>`validate_shape`</b>: See variables.Variable.__init__.
* <b>`name`</b>: See variables.Variable.__init__.
* <b>`use_resource`</b>: If `True` use a ResourceVariable instead of a Variable.

#### Returns:

New variable.