<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.leaky_relu" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.leaky_relu

Compute the Leaky ReLU activation function.

### Aliases:

* `tf.compat.v1.nn.leaky_relu`
* `tf.compat.v2.nn.leaky_relu`
* `tf.nn.leaky_relu`

``` python
tf.nn.leaky_relu(
    features,
    alpha=0.2,
    name=None
)
```



Defined in [`python/ops/nn_ops.py`](/code/stable/tensorflow/python/ops/nn_ops.py).

<!-- Placeholder for "Used in" -->

Source: [Rectifier Nonlinearities Improve Neural Network Acoustic Models. 
AL Maas, AY Hannun, AY Ng - Proc. ICML, 2013](https://ai.stanford.edu/~amaas/papers/relu_hybrid_icml2013_final.pdf).

#### Args:


* <b>`features`</b>: A `Tensor` representing preactivation values. Must be one of
  the following types: `float16`, `float32`, `float64`, `int32`, `int64`.
* <b>`alpha`</b>: Slope of the activation function at x < 0.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The activation value.
