<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.add_check_numerics_ops" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.add_check_numerics_ops

Connect a <a href="../../../tf/debugging/check_numerics.md"><code>tf.debugging.check_numerics</code></a> to every floating point tensor.

``` python
tf.compat.v1.add_check_numerics_ops()
```



Defined in [`python/ops/numerics.py`](/code/stable/tensorflow/python/ops/numerics.py).

<!-- Placeholder for "Used in" -->

`check_numerics` operations themselves are added for each `half`, `float`,
or `double` tensor in the current default graph. For all ops in the graph, the
`check_numerics` op for all of its (`half`, `float`, or `double`) inputs
is guaranteed to run before the `check_numerics` op on any of its outputs.

Note: This API is not compatible with the use of <a href="../../../tf/cond.md"><code>tf.cond</code></a> or
<a href="../../../tf/while_loop.md"><code>tf.while_loop</code></a>, and will raise a `ValueError` if you attempt to call it
in such a graph.

#### Returns:

A `group` op depending on all `check_numerics` ops added.



#### Raises:


* <b>`ValueError`</b>: If the graph contains any numeric operations in a control flow
  structure.
* <b>`RuntimeError`</b>: If called with eager execution enabled.



#### Eager Compatibility
Not compatible with eager execution. To check for `Inf`s and `NaN`s under
eager execution, call `tfe.seterr(inf_or_nan='raise')` once before executing
the checked operations.

