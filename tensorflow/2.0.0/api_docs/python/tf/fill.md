<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.fill" />
<meta itemprop="path" content="Stable" />
</div>

# tf.fill

``` python
tf.fill(
    dims,
    value,
    name=None
)
```



Defined in [`tensorflow/python/ops/array_ops.py`](/code/stable/tensorflow/python/ops/array_ops.py).

Creates a tensor filled with a scalar value.

This operation creates a tensor of shape `dims` and fills it with `value`.

For example:

```
# Output tensor has shape [2, 3].
fill([2, 3], 9) ==> [[9, 9, 9]
                     [9, 9, 9]]
```

<a href="../tf/fill.md"><code>tf.fill</code></a> differs from <a href="../tf/constant.md"><code>tf.constant</code></a> in a few ways:

*   <a href="../tf/fill.md"><code>tf.fill</code></a> only supports scalar contents, whereas <a href="../tf/constant.md"><code>tf.constant</code></a> supports
    Tensor values.
*   <a href="../tf/fill.md"><code>tf.fill</code></a> creates an Op in the computation graph that constructs the
actual
    Tensor value at runtime. This is in contrast to <a href="../tf/constant.md"><code>tf.constant</code></a> which embeds
    the entire Tensor into the graph with a `Const` node.
*   Because <a href="../tf/fill.md"><code>tf.fill</code></a> evaluates at graph runtime, it supports dynamic shapes
    based on other runtime Tensors, unlike <a href="../tf/constant.md"><code>tf.constant</code></a>.

#### Args:

* <b>`dims`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`. 1-D.
    Represents the shape of the output tensor.
* <b>`value`</b>: A `Tensor`. 0-D (scalar). Value to fill the returned tensor.
    @compatibility(numpy) Equivalent to np.full @end_compatibility
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `value`.