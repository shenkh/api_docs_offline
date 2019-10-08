<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.assert_negative" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.assert_negative

``` python
tf.debugging.assert_negative(
    x,
    message=None,
    summarize=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/check_ops.py`](/code/stable/tensorflow/python/ops/check_ops.py).

Assert the condition `x < 0` holds element-wise.

This Op checks that `x[i] < 0` holds for every element of `x`. If `x` is
empty, this is trivially satisfied.

If `x` is not negative everywhere, `message`, as well as the first `summarize`
entries of `x` are printed, and `InvalidArgumentError` is raised.

#### Args:

* <b>`x`</b>:  Numeric `Tensor`.
* <b>`message`</b>: A string to prefix to the default message.
* <b>`summarize`</b>: Print this many entries of each tensor.
* <b>`name`</b>: A name for this operation (optional).  Defaults to "assert_negative".


#### Returns:

Op raising `InvalidArgumentError` unless `x` is all negative. This can be
  used with <a href="../../tf/control_dependencies.md"><code>tf.control_dependencies</code></a> inside of <a href="../../tf/function.md"><code>tf.function</code></a>s to block
  followup computation until the check has executed.



#### Raises:

* <b>`InvalidArgumentError`</b>: if the check can be performed immediately and
    `x[i] < 0` is False. The check can be performed immediately during eager
    execution or if `x` is statically known.

#### Eager Compatibility
returns None

