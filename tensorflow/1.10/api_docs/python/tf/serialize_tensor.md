<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.serialize_tensor" />
</div>

# tf.serialize_tensor

``` python
tf.serialize_tensor(
    tensor,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_parsing_ops.py`.

Transforms a Tensor into a serialized TensorProto proto.

#### Args:

* <b>`tensor`</b>: A `Tensor`. A Tensor of type `T`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `string`.