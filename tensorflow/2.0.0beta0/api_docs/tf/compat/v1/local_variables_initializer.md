<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.local_variables_initializer" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.local_variables_initializer

Returns an Op that initializes all local variables.

### Aliases:

* `tf.compat.v1.initializers.local_variables`
* `tf.compat.v1.local_variables_initializer`

``` python
tf.compat.v1.local_variables_initializer()
```



Defined in [`python/ops/variables.py`](/code/stable/tensorflow/python/ops/variables.py).

<!-- Placeholder for "Used in" -->

This is just a shortcut for `variables_initializer(local_variables())`

#### Returns:

An Op that initializes all local variables in the graph.
