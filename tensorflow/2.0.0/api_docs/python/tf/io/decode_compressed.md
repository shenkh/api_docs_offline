<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.decode_compressed" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.decode_compressed

``` python
tf.io.decode_compressed(
    bytes,
    compression_type='',
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_parsing_ops.py`.

Decompress strings.

This op decompresses each element of the `bytes` input `Tensor`, which
is assumed to be compressed using the given `compression_type`.

The `output` is a string `Tensor` of the same shape as `bytes`,
each element containing the decompressed data from the corresponding
element in `bytes`.

#### Args:

* <b>`bytes`</b>: A `Tensor` of type `string`.
    A Tensor of string which is compressed.
* <b>`compression_type`</b>: An optional `string`. Defaults to `""`.
    A scalar containing either (i) the empty string (no
    compression), (ii) "ZLIB", or (iii) "GZIP".
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `string`.