<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.decode_json_example" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.decode_json_example

### Aliases:

* `tf.decode_json_example`
* `tf.io.decode_json_example`

``` python
tf.io.decode_json_example(
    json_examples,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_parsing_ops.py`.

See the guide: [Inputs and Readers > Converting](../../../../api_guides/python/io_ops.md#Converting)

Convert JSON-encoded Example records to binary protocol buffer strings.

This op translates a tensor containing Example records, encoded using
the [standard JSON
mapping](https://developers.google.com/protocol-buffers/docs/proto3#json),
into a tensor containing the same records encoded as binary protocol
buffers. The resulting tensor can then be fed to any of the other
Example-parsing ops.

#### Args:

* <b>`json_examples`</b>: A `Tensor` of type `string`.
    Each string is a JSON object serialized according to the JSON
    mapping of the Example proto.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `string`.