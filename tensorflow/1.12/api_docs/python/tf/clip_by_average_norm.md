<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.clip_by_average_norm" />
<meta itemprop="path" content="Stable" />
</div>

# tf.clip_by_average_norm

``` python
tf.clip_by_average_norm(
    t,
    clip_norm,
    name=None
)
```



Defined in [`tensorflow/python/ops/clip_ops.py`](/code/stable/tensorflow/python/ops/clip_ops.py).

Clips tensor values to a maximum average L2-norm.

Given a tensor `t`, and a maximum clip value `clip_norm`, this operation
normalizes `t` so that its average L2-norm is less than or equal to
`clip_norm`. Specifically, if the average L2-norm is already less than or
equal to `clip_norm`, then `t` is not modified. If the average L2-norm is
greater than `clip_norm`, then this operation returns a tensor of the same
type and shape as `t` with its values set to:

`t * clip_norm / l2norm_avg(t)`

In this case, the average L2-norm of the output tensor is `clip_norm`.

This operation is typically used to clip gradients before applying them with
an optimizer.

#### Args:

* <b>`t`</b>: A `Tensor`.
* <b>`clip_norm`</b>: A 0-D (scalar) `Tensor` > 0. A maximum clipping value.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A clipped `Tensor`.