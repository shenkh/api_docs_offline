<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.train.sdca_shrink_l1" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.train.sdca_shrink_l1

Applies L1 regularization shrink step on the parameters.

``` python
tf.compat.v1.train.sdca_shrink_l1(
    weights,
    l1,
    l2,
    name=None
)
```



Defined in generated file: `python/ops/gen_sdca_ops.py`.

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`weights`</b>: A list of `Tensor` objects with type mutable `float32`.
  a list of vectors where each value is the weight associated with a
  feature group.
* <b>`l1`</b>: A `float`. Symmetric l1 regularization strength.
* <b>`l2`</b>: A `float`.
  Symmetric l2 regularization strength. Should be a positive float.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The created Operation.
