<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.assert_greater_equal" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.assert_greater_equal

Assert the condition `x >= y` holds element-wise.

### Aliases:

* `tf.compat.v1.assert_greater_equal`
* `tf.compat.v1.debugging.assert_greater_equal`

``` python
tf.compat.v1.assert_greater_equal(
    x,
    y,
    data=None,
    summarize=None,
    message=None,
    name=None
)
```



Defined in [`python/ops/check_ops.py`](/code/stable/tensorflow/python/ops/check_ops.py).

<!-- Placeholder for "Used in" -->

Example of adding a dependency to an operation:

```python
with tf.control_dependencies([tf.compat.v1.assert_greater_equal(x, y)]):
  output = tf.reduce_sum(x)
```

This condition holds if for every pair of (possibly broadcast) elements
`x[i]`, `y[i]`, we have `x[i] >= y[i]`.
If both `x` and `y` are empty, this is trivially satisfied.

#### Args:


* <b>`x`</b>:  Numeric `Tensor`.
* <b>`y`</b>:  Numeric `Tensor`, same dtype as and broadcastable to `x`.
* <b>`data`</b>:  The tensors to print out if the condition is False.  Defaults to
  error message and first few entries of `x`, `y`.
* <b>`summarize`</b>: Print this many entries of each tensor.
* <b>`message`</b>: A string to prefix to the default message.
* <b>`name`</b>: A name for this operation (optional).  Defaults to
  "assert_greater_equal"


#### Returns:

Op that raises `InvalidArgumentError` if `x >= y` is False.
