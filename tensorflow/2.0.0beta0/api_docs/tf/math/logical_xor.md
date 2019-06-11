<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.logical_xor" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.logical_xor

Logical XOR function.

### Aliases:

* `tf.RaggedTensor.__xor__`
* `tf.compat.v1.RaggedTensor.__xor__`
* `tf.compat.v1.logical_xor`
* `tf.compat.v1.math.logical_xor`
* `tf.compat.v2.RaggedTensor.__xor__`
* `tf.compat.v2.math.logical_xor`
* `tf.math.logical_xor`

``` python
tf.math.logical_xor(
    x,
    y,
    name='LogicalXor'
)
```



Defined in [`python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

<!-- Placeholder for "Used in" -->

x ^ y = (x | y) & ~(x & y)

Inputs are tensor and if the tensors contains more than one element, an
element-wise logical XOR is computed.

#### Usage:



```python
x = tf.constant([False, False, True, True], dtype = tf.bool)
y = tf.constant([False, True, False, True], dtype = tf.bool)
z = tf.logical_xor(x, y, name="LogicalXor")
#  here z = [False  True  True False]
```

#### Args:


* <b>`x`</b>: A `Tensor` type bool.
* <b>`y`</b>: A `Tensor` of type bool.


#### Returns:

A `Tensor` of type bool with the same size as that of x or y.
