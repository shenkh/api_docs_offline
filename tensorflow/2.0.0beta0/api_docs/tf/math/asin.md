<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.asin" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.asin

Computes the trignometric inverse sine of x element-wise.

### Aliases:

* `tf.asin`
* `tf.compat.v1.asin`
* `tf.compat.v1.math.asin`
* `tf.compat.v2.asin`
* `tf.compat.v2.math.asin`
* `tf.math.asin`

``` python
tf.math.asin(
    x,
    name=None
)
```



Defined in generated file: `python/ops/gen_math_ops.py`.

<!-- Placeholder for "Used in" -->

The <a href="../../tf/math/asin.md"><code>tf.math.asin</code></a> operation returns the inverse of <a href="../../tf/math/sin.md"><code>tf.math.sin</code></a>, such that
if `y = tf.math.sin(x)` then, `x = tf.math.asin(y)`.

**Note**: The output of <a href="../../tf/math/asin.md"><code>tf.math.asin</code></a> will lie within the invertible range 
of sine, i.e [-pi/2, pi/2].

#### For example:



```python
# Note: [1.047, 0.785] ~= [(pi/3), (pi/4)]
x = tf.constant([1.047, 0.785])
y = tf.math.sin(x) # [0.8659266, 0.7068252]

tf.math.asin(y) # [1.047, 0.785] = x
```

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.
