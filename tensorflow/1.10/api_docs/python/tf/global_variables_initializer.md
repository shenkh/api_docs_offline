<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.global_variables_initializer" />
</div>

# tf.global_variables_initializer

### Aliases:

* `tf.global_variables_initializer`
* `tf.initializers.global_variables`

``` python
tf.global_variables_initializer()
```



Defined in [`tensorflow/python/ops/variables.py`](https://www.tensorflow.org/code/tensorflow/python/ops/variables.py).

See the guide: [Variables > Variable helper functions](../../../api_guides/python/state_ops.md#Variable_helper_functions)

Returns an Op that initializes global variables.

This is just a shortcut for `variables_initializer(global_variables())`

#### Returns:

An Op that initializes global variables in the graph.