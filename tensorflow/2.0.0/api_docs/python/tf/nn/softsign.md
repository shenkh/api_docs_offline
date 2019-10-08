<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.softsign" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.softsign

### Aliases:

* `tf.math.softsign`
* `tf.nn.softsign`

``` python
tf.nn.softsign(
    features,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_nn_ops.py`.

Computes softsign: `features / (abs(features) + 1)`.

#### Args:

* <b>`features`</b>: A `Tensor`. Must be one of the following types: `half`, `bfloat16`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `features`.