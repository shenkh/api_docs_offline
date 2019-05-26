<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.stateless.stateless_truncated_normal" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.stateless.stateless_truncated_normal

``` python
tf.contrib.stateless.stateless_truncated_normal(
    shape,
    seed,
    dtype=tf.float32,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_stateless_random_ops.py`.

Outputs deterministic pseudorandom values from a truncated normal distribution.

The generated values follow a normal distribution with mean 0 and standard
deviation 1, except that values whose magnitude is more than 2 standard
deviations from the mean are dropped and re-picked.

The outputs are a deterministic function of `shape` and `seed`.

#### Args:

* <b>`shape`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
    The shape of the output tensor.
* <b>`seed`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
    2 seeds (shape [2]).
* <b>`dtype`</b>: An optional <a href="../../../tf/dtypes/DType.md"><code>tf.DType</code></a> from: `tf.half, tf.float32, tf.float64`. Defaults to <a href="../../../tf.md#float32"><code>tf.float32</code></a>.
    The type of the output.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `dtype`.