<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.batch_norm_with_global_normalization" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.batch_norm_with_global_normalization

``` python
tf.nn.batch_norm_with_global_normalization(
    input,
    mean,
    variance,
    beta,
    gamma,
    variance_epsilon,
    scale_after_normalization,
    name=None
)
```



Defined in [`tensorflow/python/ops/nn_impl.py`](/code/stable/tensorflow/python/ops/nn_impl.py).

Batch normalization.

This op is deprecated. See <a href="../../tf/nn/batch_normalization.md"><code>tf.nn.batch_normalization</code></a>.

#### Args:

* <b>`input`</b>: A 4D input Tensor.
* <b>`mean`</b>: A 1D mean Tensor with size matching the last dimension of t.
    This is the first output from tf.nn.moments,
    or a saved moving average thereof.
* <b>`variance`</b>: A 1D variance Tensor with size matching the last dimension of t.
    This is the second output from tf.nn.moments,
    or a saved moving average thereof.
* <b>`beta`</b>: A 1D beta Tensor with size matching the last dimension of t.
    An offset to be added to the normalized tensor.
* <b>`gamma`</b>: A 1D gamma Tensor with size matching the last dimension of t.
    If "scale_after_normalization" is true, this tensor will be multiplied
    with the normalized tensor.
* <b>`variance_epsilon`</b>: A small float number to avoid dividing by 0.
* <b>`scale_after_normalization`</b>: A bool indicating whether the resulted tensor
    needs to be multiplied with gamma.
* <b>`name`</b>: A name for this operation (optional).


#### Returns:

A batch-normalized `t`.