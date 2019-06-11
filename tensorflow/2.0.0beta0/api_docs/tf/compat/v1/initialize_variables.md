<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.initialize_variables" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.initialize_variables

See <a href="../../../tf/compat/v1/variables_initializer.md"><code>tf.compat.v1.variables_initializer</code></a>. (deprecated)

``` python
tf.compat.v1.initialize_variables(
    var_list,
    name='init'
)
```



Defined in [`python/ops/variables.py`](/code/stable/tensorflow/python/ops/variables.py).

<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed after 2017-03-02.
Instructions for updating:
Use `tf.variables_initializer` instead.

  **NOTE** The output of this function should be used.  If it is not, a warning will be logged.  To mark the output as used, call its .mark_used() method.