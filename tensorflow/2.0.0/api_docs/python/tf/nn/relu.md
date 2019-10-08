<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.relu" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.relu

``` python
tf.nn.relu(
    features,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_nn_ops.py`.

Computes rectified linear: `max(features, 0)`.

#### Args:

* <b>`features`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `uint8`, `int16`, `int8`, `int64`, `bfloat16`, `uint16`, `half`, `uint32`, `uint64`, `qint8`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `features`.