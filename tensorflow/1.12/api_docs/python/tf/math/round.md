<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.round" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.round

### Aliases:

* `tf.math.round`
* `tf.round`

``` python
tf.math.round(
    x,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

Rounds the values of a tensor to the nearest integer, element-wise.

Rounds half to even.  Also known as bankers rounding. If you want to round
according to the current system rounding mode use tf::cint.
For example:

```python
x = tf.constant([0.9, 2.5, 2.3, 1.5, -4.5])
tf.round(x)  # [ 1.0, 2.0, 2.0, 2.0, -4.0 ]
```

#### Args:

* <b>`x`</b>: A `Tensor` of type `float16`, `float32`, `float64`, `int32`, or `int64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of same shape and type as `x`.