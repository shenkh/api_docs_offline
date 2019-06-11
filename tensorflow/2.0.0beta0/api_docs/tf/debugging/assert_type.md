<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.assert_type" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.assert_type

Asserts that the given `Tensor` is of the specified type.

### Aliases:

* `tf.compat.v2.debugging.assert_type`
* `tf.debugging.assert_type`

``` python
tf.debugging.assert_type(
    tensor,
    tf_type,
    message=None,
    name=None
)
```



Defined in [`python/ops/check_ops.py`](/code/stable/tensorflow/python/ops/check_ops.py).

<!-- Placeholder for "Used in" -->

This can always be checked statically, so this method returns nothing.

#### Args:


* <b>`tensor`</b>: A `Tensor`.
* <b>`tf_type`</b>: A tensorflow type (`dtypes.float32`, <a href="../../tf.md#int64"><code>tf.int64</code></a>, `dtypes.bool`,
  etc).
* <b>`message`</b>: A string to prefix to the default message.
* <b>`name`</b>:  A name for this operation. Defaults to "assert_type"


#### Raises:


* <b>`TypeError`</b>: If the tensor's data type doesn't match `tf_type`.