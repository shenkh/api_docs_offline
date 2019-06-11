<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.softmax" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.softmax

Computes softmax activations.

### Aliases:

* `tf.compat.v2.math.softmax`
* `tf.compat.v2.nn.softmax`
* `tf.math.softmax`
* `tf.nn.softmax`

``` python
tf.nn.softmax(
    logits,
    axis=None,
    name=None
)
```



Defined in [`python/ops/nn_ops.py`](/code/stable/tensorflow/python/ops/nn_ops.py).

<!-- Placeholder for "Used in" -->

This function performs the equivalent of

    softmax = tf.exp(logits) / tf.reduce_sum(tf.exp(logits), axis)

#### Args:


* <b>`logits`</b>: A non-empty `Tensor`. Must be one of the following types: `half`,
  `float32`, `float64`.
* <b>`axis`</b>: The dimension softmax would be performed on. The default is -1 which
  indicates the last dimension.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type and shape as `logits`.



#### Raises:


* <b>`InvalidArgumentError`</b>: if `logits` is empty or `axis` is beyond the last
  dimension of `logits`.