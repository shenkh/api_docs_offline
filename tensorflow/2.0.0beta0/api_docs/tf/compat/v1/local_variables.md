<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.local_variables" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.local_variables

Returns local variables.

``` python
tf.compat.v1.local_variables(scope=None)
```



Defined in [`python/ops/variables.py`](/code/stable/tensorflow/python/ops/variables.py).

<!-- Placeholder for "Used in" -->

Local variables - per process variables, usually not saved/restored to
checkpoint and used for temporary or intermediate values.
For example, they can be used as counters for metrics computation or
number of epochs this machine has read data.
The `tf.contrib.framework.local_variable()` function automatically adds the
new variable to `GraphKeys.LOCAL_VARIABLES`.
This convenience function returns the contents of that collection.

An alternative to local variables are global variables. See
<a href="../../../tf/compat/v1/global_variables.md"><code>tf.compat.v1.global_variables</code></a>

#### Args:


* <b>`scope`</b>: (Optional.) A string. If supplied, the resulting list is filtered
  to include only items whose `name` attribute matches `scope` using
  `re.match`. Items without a `name` attribute are never returned if a
  scope is supplied. The choice of `re.match` means that a `scope` without
  special tokens filters by prefix.


#### Returns:

A list of local `Variable` objects.
