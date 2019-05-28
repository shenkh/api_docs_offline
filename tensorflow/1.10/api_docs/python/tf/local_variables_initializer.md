<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.local_variables_initializer" />
</div>

# tf.local_variables_initializer

### Aliases:

* `tf.initializers.local_variables`
* `tf.local_variables_initializer`

``` python
tf.local_variables_initializer()
```



Defined in [`tensorflow/python/ops/variables.py`](https://www.tensorflow.org/code/tensorflow/python/ops/variables.py).

See the guide: [Variables > Variable helper functions](../../../api_guides/python/state_ops.md#Variable_helper_functions)

Returns an Op that initializes all local variables.

This is just a shortcut for `variables_initializer(local_variables())`

#### Returns:

An Op that initializes all local variables in the graph.