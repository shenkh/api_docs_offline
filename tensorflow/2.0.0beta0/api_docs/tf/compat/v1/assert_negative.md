<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.assert_negative" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.assert_negative

Assert the condition `x < 0` holds element-wise.

### Aliases:

* `tf.compat.v1.assert_negative`
* `tf.compat.v1.debugging.assert_negative`

``` python
tf.compat.v1.assert_negative(
    x,
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
with tf.control_dependencies([tf.compat.v1.assert_negative(x)]):
  output = tf.reduce_sum(x)
```

Negative means, for every element `x[i]` of `x`, we have `x[i] < 0`.
If `x` is empty this is trivially satisfied.

#### Args:


* <b>`x`</b>:  Numeric `Tensor`.
* <b>`data`</b>:  The tensors to print out if the condition is False.  Defaults to
  error message and first few entries of `x`.
* <b>`summarize`</b>: Print this many entries of each tensor.
* <b>`message`</b>: A string to prefix to the default message.
* <b>`name`</b>: A name for this operation (optional).  Defaults to "assert_negative".


#### Returns:

Op raising `InvalidArgumentError` unless `x` is all negative.
