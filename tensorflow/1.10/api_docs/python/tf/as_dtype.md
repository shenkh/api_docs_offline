<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.as_dtype" />
</div>

# tf.as_dtype

``` python
tf.as_dtype(type_value)
```



Defined in [`tensorflow/python/framework/dtypes.py`](https://www.tensorflow.org/code/tensorflow/python/framework/dtypes.py).

See the guide: [Building Graphs > Tensor types](../../../api_guides/python/framework.md#Tensor_types)

Converts the given `type_value` to a `DType`.

#### Args:

* <b>`type_value`</b>: A value that can be converted to a <a href="../tf/DType.md"><code>tf.DType</code></a> object. This may
    currently be a <a href="../tf/DType.md"><code>tf.DType</code></a> object, a [`DataType`
    enum](https://www.tensorflow.org/code/tensorflow/core/framework/types.proto),
    a string type name, or a `numpy.dtype`.


#### Returns:

A `DType` corresponding to `type_value`.


#### Raises:

* <b>`TypeError`</b>: If `type_value` cannot be converted to a `DType`.