<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.atan" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.atan

### Aliases:

* `tf.atan`
* `tf.math.atan`

``` python
tf.math.atan(
    x,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Computes the trignometric inverse tangent of x element-wise.

The <a href="../../tf/math/atan.md"><code>tf.math.atan</code></a> operation returns the inverse of <a href="../../tf/math/tan.md"><code>tf.math.tan</code></a>, such that
if `y = tf.math.tan(x)` then, `x = tf.math.atan(y)`.

**Note**: The output of <a href="../../tf/math/atan.md"><code>tf.math.atan</code></a> will lie within the invertible range 
of tan, i.e (-pi/2, pi/2).

For example:

```python
# Note: [1.047, 0.785] ~= [(pi/3), (pi/4)]
x = tf.constant([1.047, 0.785])
y = tf.math.tan(x) # [1.731261, 0.99920404]

tf.math.atan(y) # [1.047, 0.785] = x
```

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.