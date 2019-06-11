<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.decode_raw" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.decode_raw

Convert raw byte strings into tensors. (deprecated arguments)

### Aliases:

* `tf.compat.v1.decode_raw`
* `tf.compat.v1.io.decode_raw`

``` python
tf.compat.v1.decode_raw(
    input_bytes=None,
    out_type=None,
    little_endian=True,
    name=None,
    bytes=None
)
```



Defined in [`python/ops/parsing_ops.py`](/code/stable/tensorflow/python/ops/parsing_ops.py).

<!-- Placeholder for "Used in" -->

Warning: SOME ARGUMENTS ARE DEPRECATED: `(bytes)`. They will be removed in a future version.
Instructions for updating:
bytes is deprecated, use input_bytes instead

#### Args:


* <b>`input_bytes`</b>:   Each element of the input Tensor is converted to an array of bytes.
* <b>`out_type`</b>:   `DType` of the output. Acceptable types are `half`, `float`, `double`,
  `int32`, `uint16`, `uint8`, `int16`, `int8`, `int64`.
* <b>`little_endian`</b>:   Whether the `input_bytes` data is in little-endian format. Data will be
  converted into host byte order if necessary.
* <b>`name`</b>: A name for the operation (optional).
* <b>`bytes`</b>: Deprecated parameter. Use `input_bytes` instead.


#### Returns:

A `Tensor` object storing the decoded bytes.
