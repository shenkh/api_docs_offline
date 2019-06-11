<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.is_non_decreasing" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.is_non_decreasing

Returns `True` if `x` is non-decreasing.

### Aliases:

* `tf.compat.v1.debugging.is_non_decreasing`
* `tf.compat.v1.is_non_decreasing`
* `tf.compat.v1.math.is_non_decreasing`
* `tf.compat.v2.math.is_non_decreasing`
* `tf.math.is_non_decreasing`

``` python
tf.math.is_non_decreasing(
    x,
    name=None
)
```



Defined in [`python/ops/check_ops.py`](/code/stable/tensorflow/python/ops/check_ops.py).

<!-- Placeholder for "Used in" -->

Elements of `x` are compared in row-major order.  The tensor `[x[0],...]`
is non-decreasing if for every adjacent pair we have `x[i] <= x[i+1]`.
If `x` has less than two elements, it is trivially non-decreasing.

See also:  `is_strictly_increasing`

#### Args:


* <b>`x`</b>: Numeric `Tensor`.
* <b>`name`</b>: A name for this operation (optional).  Defaults to "is_non_decreasing"


#### Returns:

Boolean `Tensor`, equal to `True` iff `x` is non-decreasing.



#### Raises:


* <b>`TypeError`</b>: if `x` is not a numeric tensor.