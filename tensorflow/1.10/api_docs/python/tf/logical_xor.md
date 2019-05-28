<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.logical_xor" />
</div>

# tf.logical_xor

``` python
tf.logical_xor(
    x,
    y,
    name='LogicalXor'
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

See the guide: [Control Flow > Logical Operators](../../../api_guides/python/control_flow_ops.md#Logical_Operators)

x ^ y = (x | y) & ~(x & y).