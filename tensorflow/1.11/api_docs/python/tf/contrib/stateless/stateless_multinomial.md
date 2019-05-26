<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.stateless.stateless_multinomial" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.stateless.stateless_multinomial

``` python
tf.contrib.stateless.stateless_multinomial(
    logits,
    num_samples,
    seed,
    output_dtype=tf.int64,
    name=None
)
```



Defined in generated file: `tensorflow/contrib/stateless/gen_stateless_random_ops.py`.

TODO: add doc.

#### Args:

* <b>`logits`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `uint8`, `int16`, `int8`, `int64`, `bfloat16`, `uint16`, `half`, `uint32`, `uint64`.
* <b>`num_samples`</b>: A `Tensor` of type `int32`.
* <b>`seed`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
* <b>`output_dtype`</b>: An optional <a href="../../../tf/DType.md"><code>tf.DType</code></a> from: `tf.int32, tf.int64`. Defaults to <a href="../../../tf/int64.md"><code>tf.int64</code></a>.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `output_dtype`.