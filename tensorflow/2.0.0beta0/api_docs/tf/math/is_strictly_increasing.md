<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.is_strictly_increasing" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.is_strictly_increasing

Returns `True` if `x` is strictly increasing.

### Aliases:

* `tf.compat.v1.debugging.is_strictly_increasing`
* `tf.compat.v1.is_strictly_increasing`
* `tf.compat.v1.math.is_strictly_increasing`
* `tf.compat.v2.math.is_strictly_increasing`
* `tf.math.is_strictly_increasing`

``` python
tf.math.is_strictly_increasing(
    x,
    name=None
)
```



Defined in [`python/ops/check_ops.py`](/code/stable/tensorflow/python/ops/check_ops.py).

<!-- Placeholder for "Used in" -->

Elements of `x` are compared in row-major order.  The tensor `[x[0],...]`
is strictly increasing if for every adjacent pair we have `x[i] < x[i+1]`.
If `x` has less than two elements, it is trivially strictly increasing.

See also:  `is_non_decreasing`

#### Args:


* <b>`x`</b>: Numeric `Tensor`.
* <b>`name`</b>: A name for this operation (optional).
  Defaults to "is_strictly_increasing"


#### Returns:

Boolean `Tensor`, equal to `True` iff `x` is strictly increasing.



#### Raises:


* <b>`TypeError`</b>: if `x` is not a numeric tensor.