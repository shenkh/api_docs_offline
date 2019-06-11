<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.assert_integer" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.assert_integer

Assert that `x` is of integer dtype.

### Aliases:

* `tf.compat.v2.debugging.assert_integer`
* `tf.debugging.assert_integer`

``` python
tf.debugging.assert_integer(
    x,
    message=None,
    name=None
)
```



Defined in [`python/ops/check_ops.py`](/code/stable/tensorflow/python/ops/check_ops.py).

<!-- Placeholder for "Used in" -->

If `x` has a non-integer type, `message`, as well as the dtype of `x` are
printed, and `InvalidArgumentError` is raised.

This can always be checked statically, so this method returns nothing.

#### Args:


* <b>`x`</b>: A `Tensor`.
* <b>`message`</b>: A string to prefix to the default message.
* <b>`name`</b>: A name for this operation (optional). Defaults to "assert_integer".


#### Raises:


* <b>`TypeError`</b>:  If `x.dtype` is not a non-quantized integer type.