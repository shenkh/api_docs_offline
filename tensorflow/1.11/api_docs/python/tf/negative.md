<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.negative" />
<meta itemprop="path" content="Stable" />
</div>

# tf.negative

``` python
tf.negative(
    x,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

See the guides: [Math > Basic Math Functions](../../../api_guides/python/math_ops.md#Basic_Math_Functions), [Upgrade to TensorFlow 1.0 > Upgrading your code manually](../../../api_guides/python/upgrade.md#Upgrading_your_code_manually)

Computes numerical negative value element-wise.

I.e., \(y = -x\).

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor`. Must be one of the following types: `half`,
    `float32`, `float64`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor`, respectively. Has the same type as `x`.