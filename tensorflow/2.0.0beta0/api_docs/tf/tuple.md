<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.tuple" />
<meta itemprop="path" content="Stable" />
</div>

# tf.tuple

Group tensors together.

### Aliases:

* `tf.compat.v2.tuple`
* `tf.tuple`

``` python
tf.tuple(
    tensors,
    control_inputs=None,
    name=None
)
```



Defined in [`python/ops/control_flow_ops.py`](/code/stable/tensorflow/python/ops/control_flow_ops.py).

<!-- Placeholder for "Used in" -->

This creates a tuple of tensors with the same values as the `tensors`
argument, except that the value of each tensor is only returned after the
values of all tensors have been computed.

`control_inputs` contains additional ops that have to finish before this op
finishes, but whose outputs are not returned.

This can be used as a "join" mechanism for parallel computations: all the
argument tensors can be computed in parallel, but the values of any tensor
returned by `tuple` are only available after all the parallel computations
are done.

See also <a href="../tf/group.md"><code>tf.group</code></a> and
<a href="../tf/control_dependencies.md"><code>tf.control_dependencies</code></a>.

#### Args:


* <b>`tensors`</b>: A list of `Tensor`s or `IndexedSlices`, some entries can be `None`.
* <b>`control_inputs`</b>: List of additional ops to finish before returning.
* <b>`name`</b>: (optional) A name to use as a `name_scope` for the operation.


#### Returns:

Same as `tensors`.



#### Raises:


* <b>`ValueError`</b>: If `tensors` does not contain any `Tensor` or `IndexedSlices`.
* <b>`TypeError`</b>: If `control_inputs` is not a list of `Operation` or `Tensor`
  objects.