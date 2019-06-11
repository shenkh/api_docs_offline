<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.assert_type" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.assert_type

Statically asserts that the given `Tensor` is of the specified type.

### Aliases:

* `tf.compat.v1.assert_type`
* `tf.compat.v1.debugging.assert_type`

``` python
tf.compat.v1.assert_type(
    tensor,
    tf_type,
    message=None,
    name=None
)
```



Defined in [`python/ops/check_ops.py`](/code/stable/tensorflow/python/ops/check_ops.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`tensor`</b>: A `Tensor`.
* <b>`tf_type`</b>: A tensorflow type (`dtypes.float32`, <a href="../../../tf.md#int64"><code>tf.int64</code></a>, `dtypes.bool`,
  etc).
* <b>`message`</b>: A string to prefix to the default message.
* <b>`name`</b>:  A name to give this `Op`.  Defaults to "assert_type"


#### Raises:


* <b>`TypeError`</b>: If the tensors data type doesn't match `tf_type`.


#### Returns:

A `no_op` that does nothing.  Type can be determined statically.
