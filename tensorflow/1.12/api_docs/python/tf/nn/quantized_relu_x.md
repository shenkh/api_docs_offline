<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.quantized_relu_x" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.quantized_relu_x

``` python
tf.nn.quantized_relu_x(
    features,
    max_value,
    min_features,
    max_features,
    out_type=tf.quint8,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_nn_ops.py`.

Computes Quantized Rectified Linear X: `min(max(features, 0), max_value)`

#### Args:

* <b>`features`</b>: A `Tensor`. Must be one of the following types: `qint8`, `quint8`, `qint32`, `qint16`, `quint16`.
* <b>`max_value`</b>: A `Tensor` of type `float32`.
* <b>`min_features`</b>: A `Tensor` of type `float32`.
    The float value that the lowest quantized value represents.
* <b>`max_features`</b>: A `Tensor` of type `float32`.
    The float value that the highest quantized value represents.
* <b>`out_type`</b>: An optional <a href="../../tf/dtypes/DType.md"><code>tf.DType</code></a> from: `tf.qint8, tf.quint8, tf.qint32, tf.qint16, tf.quint16`. Defaults to <a href="../../tf.md#quint8"><code>tf.quint8</code></a>.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A tuple of `Tensor` objects (activations, min_activations, max_activations).

* <b>`activations`</b>: A `Tensor` of type `out_type`.
* <b>`min_activations`</b>: A `Tensor` of type `float32`.
* <b>`max_activations`</b>: A `Tensor` of type `float32`.