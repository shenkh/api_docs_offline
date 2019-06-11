<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.is_numeric_tensor" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.is_numeric_tensor

Returns `True` if the elements of `tensor` are numbers.

### Aliases:

* `tf.compat.v1.debugging.is_numeric_tensor`
* `tf.compat.v1.is_numeric_tensor`
* `tf.compat.v2.debugging.is_numeric_tensor`
* `tf.debugging.is_numeric_tensor`

``` python
tf.debugging.is_numeric_tensor(tensor)
```



Defined in [`python/ops/check_ops.py`](/code/stable/tensorflow/python/ops/check_ops.py).

<!-- Placeholder for "Used in" -->

Specifically, returns `True` if the dtype of `tensor` is one of the following:

* <a href="../../tf.md#float32"><code>tf.float32</code></a>
* <a href="../../tf.md#float64"><code>tf.float64</code></a>
* <a href="../../tf.md#int8"><code>tf.int8</code></a>
* <a href="../../tf.md#int16"><code>tf.int16</code></a>
* <a href="../../tf.md#int32"><code>tf.int32</code></a>
* <a href="../../tf.md#int64"><code>tf.int64</code></a>
* <a href="../../tf.md#uint8"><code>tf.uint8</code></a>
* <a href="../../tf.md#qint8"><code>tf.qint8</code></a>
* <a href="../../tf.md#qint32"><code>tf.qint32</code></a>
* <a href="../../tf.md#quint8"><code>tf.quint8</code></a>
* <a href="../../tf.md#complex64"><code>tf.complex64</code></a>

Returns `False` if `tensor` is of a non-numeric type or if `tensor` is not
a <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> object.