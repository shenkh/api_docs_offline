<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.logical_xor" />
<meta itemprop="path" content="Stable" />
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

x ^ y = (x | y) & ~(x & y).