<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.square" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.square

### Aliases:

* `tf.math.square`
* `tf.square`

``` python
tf.math.square(
    x,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Computes square of x element-wise.

I.e., \\(y = x * x = x^2\\).

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

If `x` is a `SparseTensor`, returns
`SparseTensor(x.indices, tf.math.square(x.values, ...), x.dense_shape)`