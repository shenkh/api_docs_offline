<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.softplus" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.softplus

Computes softplus: `log(exp(features) + 1)`.

### Aliases:

* `tf.compat.v1.math.softplus`
* `tf.compat.v1.nn.softplus`
* `tf.compat.v2.math.softplus`
* `tf.compat.v2.nn.softplus`
* `tf.math.softplus`
* `tf.nn.softplus`

``` python
tf.math.softplus(
    features,
    name=None
)
```



Defined in generated file: `python/ops/gen_nn_ops.py`.

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`features`</b>: A `Tensor`. Must be one of the following types: `half`, `bfloat16`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `features`.
