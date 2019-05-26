<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.sqrt" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.sqrt

### Aliases:

* `tf.math.sqrt`
* `tf.sqrt`

``` python
tf.math.sqrt(
    x,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

Computes square root of x element-wise.

I.e., \\(y = \sqrt{x} = x^{1/2}\\).

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor`. Must be one of the following types: `half`,
    `float32`, `float64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor`, respectively. Has the same type as `x`.