<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary.experimental.set_step" />
<meta itemprop="path" content="Stable" />
</div>

# tf.summary.experimental.set_step

Sets the default summary step for the current thread.

### Aliases:

* `tf.compat.v2.summary.experimental.set_step`
* `tf.summary.experimental.set_step`

``` python
tf.summary.experimental.set_step(step)
```



Defined in [`python/ops/summary_ops_v2.py`](/code/stable/tensorflow/python/ops/summary_ops_v2.py).

<!-- Placeholder for "Used in" -->

For convenience, this function sets a default value for the `step` parameter
used in summary-writing functions elsewhere in the API so that it need not
be explicitly passed in every such invocation. The value can be a constant
or a variable, and can be retrieved via `tf.summary.experimental.get_step()`.

Note: when using this with @tf.functions, the step value will be captured at
the time the function is traced, so changes to the step outside the function
will not be reflected inside the function unless using a <a href="../../../tf/Variable.md"><code>tf.Variable</code></a> step.

#### Args:


* <b>`step`</b>: An `int64`-castable default step value, or None to unset.