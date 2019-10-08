<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.make_tensor_proto" />
<meta itemprop="path" content="Stable" />
</div>

# tf.make_tensor_proto

``` python
tf.make_tensor_proto(
    values,
    dtype=None,
    shape=None,
    verify_shape=False,
    allow_broadcast=False
)
```



Defined in [`tensorflow/python/framework/tensor_util.py`](/code/stable/tensorflow/python/framework/tensor_util.py).

Create a TensorProto.

In TensorFlow 2.0, representing tensors as protos should no longer be a
common workflow. That said, this utility function is still useful for
generating TF Serving request protos:

  request = tensorflow_serving.apis.predict_pb2.PredictRequest()
  request.model_spec.name = "my_model"
  request.model_spec.signature_name = "serving_default"
  request.inputs["images"].CopyFrom(tf.make_tensor_proto(X_new))

make_tensor_proto accepts "values" of a python scalar, a python list, a
numpy ndarray, or a numpy scalar.

If "values" is a python scalar or a python list, make_tensor_proto
first convert it to numpy ndarray. If dtype is None, the
conversion tries its best to infer the right numpy data
type. Otherwise, the resulting numpy array has a compatible data
type with the given dtype.

In either case above, the numpy ndarray (either the caller provided
or the auto converted) must have the compatible type with dtype.

make_tensor_proto then converts the numpy array to a tensor proto.

If "shape" is None, the resulting tensor proto represents the numpy
array precisely.

Otherwise, "shape" specifies the tensor's shape and the numpy array
can not have more elements than what "shape" specifies.

#### Args:

* <b>`values`</b>:         Values to put in the TensorProto.
* <b>`dtype`</b>:          Optional tensor_pb2 DataType value.
* <b>`shape`</b>:          List of integers representing the dimensions of tensor.
* <b>`verify_shape`</b>:   Boolean that enables verification of a shape of values.
* <b>`allow_broadcast`</b>:  Boolean that enables allowing scalars and 1 length vector
      broadcasting. Cannot be true when verify_shape is true.


#### Returns:

A `TensorProto`. Depending on the type, it may contain data in the
"tensor_content" attribute, which is not directly useful to Python programs.
To access the values you should convert the proto back to a numpy ndarray
with `tf.make_ndarray(proto)`.

If `values` is a `TensorProto`, it is immediately returned; `dtype` and
`shape` are ignored.


#### Raises:

* <b>`TypeError`</b>:  if unsupported types are provided.
* <b>`ValueError`</b>: if arguments have inappropriate values or if verify_shape is
   True and shape of values is not equals to a shape from the argument.