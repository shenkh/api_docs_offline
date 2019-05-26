<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distributions.bijectors.masked_dense" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.distributions.bijectors.masked_dense

``` python
tf.contrib.distributions.bijectors.masked_dense(
    inputs,
    units,
    num_blocks=None,
    exclusive=False,
    kernel_initializer=None,
    reuse=None,
    name=None,
    *args,
    **kwargs
)
```



Defined in [`tensorflow/contrib/distributions/python/ops/bijectors/masked_autoregressive.py`](https://www.tensorflow.org/code/tensorflow/contrib/distributions/python/ops/bijectors/masked_autoregressive.py).

A autoregressively masked dense layer. Analogous to <a href="../../../../tf/layers/dense.md"><code>tf.layers.dense</code></a>. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed after 2018-10-01.
Instructions for updating:
The TensorFlow Distributions library has moved to TensorFlow Probability (https://github.com/tensorflow/probability). You should update all references to use `tfp.distributions` instead of <a href="../../../../tf/contrib/distributions.md"><code>tf.contrib.distributions</code></a>.

See [Germain et al. (2015)][1] for detailed explanation.

#### Arguments:

* <b>`inputs`</b>: Tensor input.
* <b>`units`</b>: Python `int` scalar representing the dimensionality of the output
    space.
* <b>`num_blocks`</b>: Python `int` scalar representing the number of blocks for the
    MADE masks.
* <b>`exclusive`</b>: Python `bool` scalar representing whether to zero the diagonal of
    the mask, used for the first layer of a MADE.
* <b>`kernel_initializer`</b>: Initializer function for the weight matrix.
    If `None` (default), weights are initialized using the
    `tf.glorot_random_initializer`.
* <b>`reuse`</b>: Python `bool` scalar representing whether to reuse the weights of a
    previous layer by the same name.
* <b>`name`</b>: Python `str` used to describe ops managed by this function.
* <b>`*args`</b>: <a href="../../../../tf/layers/dense.md"><code>tf.layers.dense</code></a> arguments.
* <b>`**kwargs`</b>: <a href="../../../../tf/layers/dense.md"><code>tf.layers.dense</code></a> keyword arguments.


#### Returns:

Output tensor.


#### Raises:

* <b>`NotImplementedError`</b>: if rightmost dimension of `inputs` is unknown prior to
    graph execution.

#### References

[1]: Mathieu Germain, Karol Gregor, Iain Murray, and Hugo Larochelle. MADE:
     Masked Autoencoder for Distribution Estimation. In _International
     Conference on Machine Learning_, 2015. https://arxiv.org/abs/1502.03509