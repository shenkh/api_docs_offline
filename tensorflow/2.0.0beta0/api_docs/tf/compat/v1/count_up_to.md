<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.count_up_to" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.count_up_to

Increments 'ref' until it reaches 'limit'. (deprecated)

``` python
tf.compat.v1.count_up_to(
    ref,
    limit,
    name=None
)
```



Defined in [`python/ops/state_ops.py`](/code/stable/tensorflow/python/ops/state_ops.py).

<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Prefer Dataset.range instead.

#### Args:


* <b>`ref`</b>: A Variable. Must be one of the following types: `int32`, `int64`.
  Should be from a scalar `Variable` node.
* <b>`limit`</b>: An `int`.
  If incrementing ref would bring it above limit, instead generates an
  'OutOfRange' error.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `ref`.
A copy of the input before increment. If nothing else modifies the
input, the values produced will all be distinct.
