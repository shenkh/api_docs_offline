<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.bias_add" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.bias_add

Adds `bias` to `value`.

### Aliases:

* `tf.compat.v1.nn.bias_add`
* `tf.compat.v2.nn.bias_add`
* `tf.nn.bias_add`

``` python
tf.nn.bias_add(
    value,
    bias,
    data_format=None,
    name=None
)
```



Defined in [`python/ops/nn_ops.py`](/code/stable/tensorflow/python/ops/nn_ops.py).

<!-- Placeholder for "Used in" -->

This is (mostly) a special case of <a href="../../tf/math/add.md"><code>tf.add</code></a> where `bias` is restricted to 1-D.
Broadcasting is supported, so `value` may have any number of dimensions.
Unlike <a href="../../tf/math/add.md"><code>tf.add</code></a>, the type of `bias` is allowed to differ from `value` in the
case where both types are quantized.

#### Args:


* <b>`value`</b>: A `Tensor` with type `float`, `double`, `int64`, `int32`, `uint8`,
  `int16`, `int8`, `complex64`, or `complex128`.
* <b>`bias`</b>: A 1-D `Tensor` with size matching the last dimension of `value`.
  Must be the same type as `value` unless `value` is a quantized type,
  in which case a different quantized type may be used.
* <b>`data_format`</b>: A string. 'N...C' and 'NC...' are supported.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` with the same type as `value`.
