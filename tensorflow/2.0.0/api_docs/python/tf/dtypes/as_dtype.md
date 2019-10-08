<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.dtypes.as_dtype" />
<meta itemprop="path" content="Stable" />
</div>

# tf.dtypes.as_dtype

### Aliases:

* `tf.as_dtype`
* `tf.dtypes.as_dtype`

``` python
tf.dtypes.as_dtype(type_value)
```



Defined in [`tensorflow/python/framework/dtypes.py`](/code/stable/tensorflow/python/framework/dtypes.py).

Converts the given `type_value` to a `DType`.

#### Args:

* <b>`type_value`</b>: A value that can be converted to a <a href="../../tf/dtypes/DType.md"><code>tf.DType</code></a> object. This may
    currently be a <a href="../../tf/dtypes/DType.md"><code>tf.DType</code></a> object, a [`DataType`
    enum](https://www.tensorflow.org/code/tensorflow/core/framework/types.proto),
      a string type name, or a `numpy.dtype`.


#### Returns:

A `DType` corresponding to `type_value`.


#### Raises:

* <b>`TypeError`</b>: If `type_value` cannot be converted to a `DType`.