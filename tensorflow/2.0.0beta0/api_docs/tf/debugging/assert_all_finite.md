<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.assert_all_finite" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.assert_all_finite

Assert that the tensor does not contain any NaN's or Inf's.

### Aliases:

* `tf.compat.v2.debugging.assert_all_finite`
* `tf.debugging.assert_all_finite`

``` python
tf.debugging.assert_all_finite(
    x,
    message,
    name=None
)
```



Defined in [`python/ops/numerics.py`](/code/stable/tensorflow/python/ops/numerics.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`x`</b>: Tensor to check.
* <b>`message`</b>: Message to log on failure.
* <b>`name`</b>: A name for this operation (optional).


#### Returns:

Same tensor as `x`.
