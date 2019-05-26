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

See the guide: [Neural Network > Activation Functions](../../../../api_guides/python/nn.md#Activation_Functions)

Computes softsign: `features / (abs(features) + 1)`.

#### Args:

* <b>`features`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `uint8`, `int16`, `int8`, `int64`, `bfloat16`, `uint16`, `half`, `uint32`, `uint64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `features`.