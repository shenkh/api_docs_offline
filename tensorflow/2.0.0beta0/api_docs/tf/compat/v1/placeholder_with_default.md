<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.placeholder_with_default" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.placeholder_with_default

A placeholder op that passes through `input` when its output is not fed.

``` python
tf.compat.v1.placeholder_with_default(
    input,
    shape,
    name=None
)
```



Defined in [`python/ops/array_ops.py`](/code/stable/tensorflow/python/ops/array_ops.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`input`</b>: A `Tensor`. The default value to produce when output is not fed.
* <b>`shape`</b>: A <a href="../../../tf/TensorShape.md"><code>tf.TensorShape</code></a> or list of `int`s. The (possibly partial) shape of
  the tensor.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.
