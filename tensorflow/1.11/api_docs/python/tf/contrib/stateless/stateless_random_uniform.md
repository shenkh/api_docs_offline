<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.stateless.stateless_random_uniform" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.stateless.stateless_random_uniform

``` python
tf.contrib.stateless.stateless_random_uniform(
    shape,
    seed,
    dtype=tf.float32,
    name=None
)
```



Defined in generated file: `tensorflow/contrib/stateless/gen_stateless_random_ops.py`.

TODO: add doc.

#### Args:

* <b>`shape`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
* <b>`seed`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
* <b>`dtype`</b>: An optional <a href="../../../tf/DType.md"><code>tf.DType</code></a> from: `tf.half, tf.float32, tf.float64`. Defaults to <a href="../../../tf/float32.md"><code>tf.float32</code></a>.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `dtype`.