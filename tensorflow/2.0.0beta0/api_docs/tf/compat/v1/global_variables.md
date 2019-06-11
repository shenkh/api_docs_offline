<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.global_variables" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.global_variables

Returns global variables.

``` python
tf.compat.v1.global_variables(scope=None)
```



Defined in [`python/ops/variables.py`](/code/stable/tensorflow/python/ops/variables.py).

<!-- Placeholder for "Used in" -->

Global variables are variables that are shared across machines in a
distributed environment. The `Variable()` constructor or `get_variable()`
automatically adds new variables to the graph collection
`GraphKeys.GLOBAL_VARIABLES`.
This convenience function returns the contents of that collection.

An alternative to global variables are local variables. See
<a href="../../../tf/compat/v1/local_variables.md"><code>tf.compat.v1.local_variables</code></a>

#### Args:


* <b>`scope`</b>: (Optional.) A string. If supplied, the resulting list is filtered
  to include only items whose `name` attribute matches `scope` using
  `re.match`. Items without a `name` attribute are never returned if a
  scope is supplied. The choice of `re.match` means that a `scope` without
  special tokens filters by prefix.


#### Returns:

A list of `Variable` objects.
