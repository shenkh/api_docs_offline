<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.assert_rank" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.assert_rank

Assert that `x` has rank equal to `rank`.

### Aliases:

* `tf.assert_rank`
* `tf.compat.v2.assert_rank`
* `tf.compat.v2.debugging.assert_rank`
* `tf.debugging.assert_rank`

``` python
tf.debugging.assert_rank(
    x,
    rank,
    message=None,
    name=None
)
```



Defined in [`python/ops/check_ops.py`](/code/stable/tensorflow/python/ops/check_ops.py).

<!-- Placeholder for "Used in" -->

This Op checks that the rank of `x` is equal to `rank`.

If `x` has a different rank, `message`, as well as the shape of `x` are
printed, and `InvalidArgumentError` is raised.

#### Args:


* <b>`x`</b>: `Tensor`.
* <b>`rank`</b>: Scalar integer `Tensor`.
* <b>`message`</b>: A string to prefix to the default message.
* <b>`name`</b>: A name for this operation (optional). Defaults to
  "assert_rank".


#### Returns:

Op raising `InvalidArgumentError` unless `x` has specified rank.
If static checks determine `x` has correct rank, a `no_op` is returned.
This can be used with <a href="../../tf/control_dependencies.md"><code>tf.control_dependencies</code></a> inside of <a href="../../tf/function.md"><code>tf.function</code></a>s
to block followup computation until the check has executed.




#### Raises:


* <b>`InvalidArgumentError`</b>: if the check can be performed immediately and
  `x` does not have rank `rank`. The check can be performed immediately
  during eager execution or if the shape of `x` is statically known.

#### Eager Compatibility
returns None

