<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.parse_tensor" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.parse_tensor

### Aliases:

* `tf.io.parse_tensor`
* `tf.parse_tensor`

``` python
tf.io.parse_tensor(
    serialized,
    out_type,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_parsing_ops.py`.

Transforms a serialized tensorflow.TensorProto proto into a Tensor.

#### Args:

* <b>`serialized`</b>: A `Tensor` of type `string`.
    A scalar string containing a serialized TensorProto proto.
* <b>`out_type`</b>: A <a href="../../tf/dtypes/DType.md"><code>tf.DType</code></a>.
    The type of the serialized tensor.  The provided type must match the
    type of the serialized tensor and no implicit conversion will take place.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `out_type`.