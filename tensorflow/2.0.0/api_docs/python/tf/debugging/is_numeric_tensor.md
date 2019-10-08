<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.is_numeric_tensor" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.is_numeric_tensor

``` python
tf.debugging.is_numeric_tensor(tensor)
```



Defined in [`tensorflow/python/ops/check_ops.py`](/code/stable/tensorflow/python/ops/check_ops.py).

Returns `True` if the elements of `tensor` are numbers.

Specifically, returns `True` if the dtype of `tensor` is one of the following:

* <a href="../../tf/dtypes.md#float32"><code>tf.float32</code></a>
* <a href="../../tf/dtypes.md#double"><code>tf.float64</code></a>
* <a href="../../tf/dtypes.md#int8"><code>tf.int8</code></a>
* <a href="../../tf/dtypes.md#int16"><code>tf.int16</code></a>
* <a href="../../tf/dtypes.md#int32"><code>tf.int32</code></a>
* <a href="../../tf/dtypes.md#int64"><code>tf.int64</code></a>
* <a href="../../tf/dtypes.md#uint8"><code>tf.uint8</code></a>
* <a href="../../tf/dtypes.md#qint8"><code>tf.qint8</code></a>
* <a href="../../tf/dtypes.md#qint32"><code>tf.qint32</code></a>
* <a href="../../tf/dtypes.md#quint8"><code>tf.quint8</code></a>
* <a href="../../tf/dtypes.md#complex64"><code>tf.complex64</code></a>

Returns `False` if `tensor` is of a non-numeric type or if `tensor` is not
a <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> object.