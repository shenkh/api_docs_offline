<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.math.log_softmax" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.math.log_softmax

Computes log softmax activations. (deprecated arguments)

### Aliases:

* `tf.compat.v1.math.log_softmax`
* `tf.compat.v1.nn.log_softmax`

``` python
tf.compat.v1.math.log_softmax(
    logits,
    axis=None,
    name=None,
    dim=None
)
```



Defined in [`python/ops/nn_ops.py`](/code/stable/tensorflow/python/ops/nn_ops.py).

<!-- Placeholder for "Used in" -->

Warning: SOME ARGUMENTS ARE DEPRECATED: `(dim)`. They will be removed in a future version.
Instructions for updating:
dim is deprecated, use axis instead

For each batch `i` and class `j` we have

    logsoftmax = logits - log(reduce_sum(exp(logits), axis))

#### Args:


* <b>`logits`</b>: A non-empty `Tensor`. Must be one of the following types: `half`,
  `float32`, `float64`.
* <b>`axis`</b>: The dimension softmax would be performed on. The default is -1 which
  indicates the last dimension.
* <b>`name`</b>: A name for the operation (optional).
* <b>`dim`</b>: Deprecated alias for `axis`.


#### Returns:

A `Tensor`. Has the same type as `logits`. Same shape as `logits`.



#### Raises:


* <b>`InvalidArgumentError`</b>: if `logits` is empty or `axis` is beyond the last
  dimension of `logits`.