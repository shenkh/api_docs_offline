<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.assert_scalar" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.assert_scalar

``` python
tf.debugging.assert_scalar(
    tensor,
    message=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/check_ops.py`](/code/stable/tensorflow/python/ops/check_ops.py).

Asserts that the given `tensor` is a scalar.

This function raises `ValueError` unless it can be certain that the given
`tensor` is a scalar. `ValueError` is also raised if the shape of `tensor` is
unknown.

This is always checked statically, so this method returns nothing.

#### Args:

* <b>`tensor`</b>: A `Tensor`.
* <b>`message`</b>: A string to prefix to the default message.
* <b>`name`</b>:  A name for this operation. Defaults to "assert_scalar"


#### Raises:

* <b>`ValueError`</b>: If the tensor is not scalar (rank 0), or if its shape is
    unknown.