<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings.to_number" />
<meta itemprop="path" content="Stable" />
</div>

# tf.strings.to_number

Converts each string in the input Tensor to the specified numeric type.

### Aliases:

* `tf.compat.v2.strings.to_number`
* `tf.strings.to_number`

``` python
tf.strings.to_number(
    input,
    out_type=tf.dtypes.float32,
    name=None
)
```



Defined in [`python/ops/string_ops.py`](/code/stable/tensorflow/python/ops/string_ops.py).

<!-- Placeholder for "Used in" -->

(Note that int32 overflow results in an error while float overflow
results in a rounded value.)

#### Args:


* <b>`input`</b>: A `Tensor` of type `string`.
* <b>`out_type`</b>: An optional <a href="../../tf/dtypes/DType.md"><code>tf.DType</code></a> from: `tf.float32, tf.float64, tf.int32,
  tf.int64`. Defaults to <a href="../../tf.md#float32"><code>tf.float32</code></a>.
  The numeric type to interpret each string in `string_tensor` as.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `out_type`.
