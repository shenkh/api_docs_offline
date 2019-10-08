<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.pow" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.pow

### Aliases:

* `tf.RaggedTensor.__pow__`
* `tf.math.pow`
* `tf.pow`

``` python
tf.math.pow(
    x,
    y,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

Computes the power of one value to another.

Given a tensor `x` and a tensor `y`, this operation computes \\(x^y\\) for
corresponding elements in `x` and `y`. For example:

```python
x = tf.constant([[2, 2], [3, 3]])
y = tf.constant([[8, 16], [2, 3]])
tf.pow(x, y)  # [[256, 65536], [9, 27]]
```

#### Args:

* <b>`x`</b>: A `Tensor` of type `float16`, `float32`, `float64`, `int32`, `int64`,
    `complex64`, or `complex128`.
* <b>`y`</b>: A `Tensor` of type `float16`, `float32`, `float64`, `int32`, `int64`,
    `complex64`, or `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`.