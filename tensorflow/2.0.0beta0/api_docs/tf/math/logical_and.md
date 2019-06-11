<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.logical_and" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.logical_and

Returns the truth value of x AND y element-wise.

### Aliases:

* `tf.RaggedTensor.__and__`
* `tf.compat.v1.RaggedTensor.__and__`
* `tf.compat.v1.logical_and`
* `tf.compat.v1.math.logical_and`
* `tf.compat.v2.RaggedTensor.__and__`
* `tf.compat.v2.logical_and`
* `tf.compat.v2.math.logical_and`
* `tf.logical_and`
* `tf.math.logical_and`

``` python
tf.math.logical_and(
    x,
    y,
    name=None
)
```



Defined in generated file: `python/ops/gen_math_ops.py`.

<!-- Placeholder for "Used in" -->

*NOTE*: `math.logical_and` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:


* <b>`x`</b>: A `Tensor` of type `bool`.
* <b>`y`</b>: A `Tensor` of type `bool`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.
