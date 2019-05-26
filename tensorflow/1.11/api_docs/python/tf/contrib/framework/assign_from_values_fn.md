<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.assign_from_values_fn" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.framework.assign_from_values_fn

``` python
tf.contrib.framework.assign_from_values_fn(var_names_to_values)
```



Defined in [`tensorflow/contrib/framework/python/ops/variables.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/python/ops/variables.py).

Returns a function that assigns specific variables from the given values.

This function provides a mechanism for performing assignment of variables
to values in a way that does not fill the graph with large assignment values.

#### Args:

* <b>`var_names_to_values`</b>: A map from variable names to values.


#### Returns:

A function that takes a single argument, a <a href="../../../tf/Session.md"><code>tf.Session</code></a>, that applies the
assignment operation.


#### Raises:

* <b>`ValueError`</b>: if any of the given variable names were not found.