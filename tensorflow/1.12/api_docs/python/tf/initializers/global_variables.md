<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.initializers.global_variables" />
<meta itemprop="path" content="Stable" />
</div>

# tf.initializers.global_variables

### Aliases:

* `tf.global_variables_initializer`
* `tf.initializers.global_variables`

``` python
tf.initializers.global_variables()
```



Defined in [`tensorflow/python/ops/variables.py`](/code/stable/tensorflow/python/ops/variables.py).

Returns an Op that initializes global variables.

This is just a shortcut for `variables_initializer(global_variables())`

#### Returns:

An Op that initializes global variables in the graph.