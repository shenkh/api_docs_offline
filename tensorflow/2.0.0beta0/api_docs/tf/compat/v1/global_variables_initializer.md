<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.global_variables_initializer" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.global_variables_initializer

Returns an Op that initializes global variables.

### Aliases:

* `tf.compat.v1.global_variables_initializer`
* `tf.compat.v1.initializers.global_variables`

``` python
tf.compat.v1.global_variables_initializer()
```



Defined in [`python/ops/variables.py`](/code/stable/tensorflow/python/ops/variables.py).

<!-- Placeholder for "Used in" -->

This is just a shortcut for `variables_initializer(global_variables())`

#### Returns:

An Op that initializes global variables in the graph.
