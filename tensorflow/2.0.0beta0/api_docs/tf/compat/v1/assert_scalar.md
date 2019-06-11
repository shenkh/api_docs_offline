<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.assert_scalar" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.assert_scalar

Asserts that the given `tensor` is a scalar (i.e. zero-dimensional).

### Aliases:

* `tf.compat.v1.assert_scalar`
* `tf.compat.v1.debugging.assert_scalar`

``` python
tf.compat.v1.assert_scalar(
    tensor,
    name=None,
    message=None
)
```



Defined in [`python/ops/check_ops.py`](/code/stable/tensorflow/python/ops/check_ops.py).

<!-- Placeholder for "Used in" -->

This function raises `ValueError` unless it can be certain that the given
`tensor` is a scalar. `ValueError` is also raised if the shape of `tensor` is
unknown.

#### Args:


* <b>`tensor`</b>: A `Tensor`.
* <b>`name`</b>:  A name for this operation. Defaults to "assert_scalar"
* <b>`message`</b>: A string to prefix to the default message.


#### Returns:

The input tensor (potentially converted to a `Tensor`).



#### Raises:


* <b>`ValueError`</b>: If the tensor is not scalar (rank 0), or if its shape is
  unknown.