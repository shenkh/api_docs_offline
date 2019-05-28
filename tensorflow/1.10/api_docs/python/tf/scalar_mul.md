<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.scalar_mul" />
</div>

# tf.scalar_mul

``` python
tf.scalar_mul(
    scalar,
    x
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

See the guide: [Math > Arithmetic Operators](../../../api_guides/python/math_ops.md#Arithmetic_Operators)

Multiplies a scalar times a `Tensor` or `IndexedSlices` object.

Intended for use in gradient code which might deal with `IndexedSlices`
objects, which are easy to multiply by a scalar but more expensive to
multiply with arbitrary tensors.

#### Args:

* <b>`scalar`</b>: A 0-D scalar `Tensor`. Must have known shape.
* <b>`x`</b>: A `Tensor` or `IndexedSlices` to be scaled.


#### Returns:

`scalar * x` of the same type (`Tensor` or `IndexedSlices`) as `x`.


#### Raises:

* <b>`ValueError`</b>: if scalar is not a 0-D `scalar`.