<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.assert_less_equal" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.assert_less_equal

Assert the condition `x <= y` holds element-wise.

### Aliases:

* `tf.compat.v2.debugging.assert_less_equal`
* `tf.debugging.assert_less_equal`

``` python
tf.debugging.assert_less_equal(
    x,
    y,
    message=None,
    summarize=None,
    name=None
)
```



Defined in [`python/ops/check_ops.py`](/code/stable/tensorflow/python/ops/check_ops.py).

<!-- Placeholder for "Used in" -->

This Op checks that `x[i] <= y[i]` holds for every pair of (possibly
broadcast) elements of `x` and `y`. If both `x` and `y` are empty, this is
trivially satisfied.

If `x` is not less or equal than `y` element-wise, `message`, as well as the
first `summarize` entries of `x` and `y` are printed, and
`InvalidArgumentError` is raised.

#### Args:


* <b>`x`</b>:  Numeric `Tensor`.
* <b>`y`</b>:  Numeric `Tensor`, same dtype as and broadcastable to `x`.
* <b>`message`</b>: A string to prefix to the default message.
* <b>`summarize`</b>: Print this many entries of each tensor.
* <b>`name`</b>: A name for this operation (optional). Defaults to "assert_less_equal".


#### Returns:

Op that raises `InvalidArgumentError` if `x <= y` is False. This can be
  used with <a href="../../tf/control_dependencies.md"><code>tf.control_dependencies</code></a> inside of <a href="../../tf/function.md"><code>tf.function</code></a>s to block
  followup computation until the check has executed.




#### Raises:


* <b>`InvalidArgumentError`</b>: if the check can be performed immediately and
  `x <= y` is False. The check can be performed immediately during eager
  execution or if `x` and `y` are statically known.

#### Eager Compatibility
returns None

