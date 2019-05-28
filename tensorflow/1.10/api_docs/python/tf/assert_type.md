<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.assert_type" />
</div>

# tf.assert_type

``` python
tf.assert_type(
    tensor,
    tf_type,
    message=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/check_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/check_ops.py).

See the guide: [Asserts and boolean checks](../../../api_guides/python/check_ops.md)

Statically asserts that the given `Tensor` is of the specified type.

#### Args:

* <b>`tensor`</b>: A tensorflow `Tensor`.
* <b>`tf_type`</b>: A tensorflow type (`dtypes.float32`, <a href="../tf/int64.md"><code>tf.int64</code></a>, `dtypes.bool`,
    etc).
* <b>`message`</b>: A string to prefix to the default message.
* <b>`name`</b>:  A name to give this `Op`.  Defaults to "assert_type"


#### Raises:

* <b>`TypeError`</b>: If the tensors data type doesn't match `tf_type`.


#### Returns:

A `no_op` that does nothing.  Type can be determined statically.