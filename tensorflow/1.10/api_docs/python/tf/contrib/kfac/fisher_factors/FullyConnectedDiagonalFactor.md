<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.fisher_factors.FullyConnectedDiagonalFactor" />
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get_cholesky"/>
<meta itemprop="property" content="get_cholesky_inverse"/>
<meta itemprop="property" content="get_cov"/>
<meta itemprop="property" content="get_cov_as_linear_operator"/>
<meta itemprop="property" content="get_matpower"/>
<meta itemprop="property" content="instantiate_cov_variables"/>
<meta itemprop="property" content="instantiate_inv_variables"/>
<meta itemprop="property" content="make_covariance_update_op"/>
<meta itemprop="property" content="make_inverse_update_ops"/>
<meta itemprop="property" content="register_cholesky"/>
<meta itemprop="property" content="register_cholesky_inverse"/>
<meta itemprop="property" content="register_matpower"/>
</div>

# tf.contrib.kfac.fisher_factors.FullyConnectedDiagonalFactor

## Class `FullyConnectedDiagonalFactor`

Inherits From: [`DiagonalFactor`](../../../../tf/contrib/kfac/fisher_factors/DiagonalFactor.md)



Defined in [`tensorflow/contrib/kfac/python/ops/fisher_factors.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/fisher_factors.py).

FisherFactor for a diagonal approx of a fully-connected layer's Fisher.

Given in = [batch_size, input_size] and out_grad = [batch_size, output_size],
approximates the covariance as,

  Cov(in, out) = (1/batch_size) sum_{i} outer(in[i], out_grad[i]) ** 2.0

where the square is taken element-wise.

## Properties

<h3 id="name"><code>name</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    inputs,
    outputs_grads,
    has_bias=False
)
```

Instantiate FullyConnectedDiagonalFactor.

#### Args:

* <b>`inputs`</b>: List of Tensors of shape [batch_size, input_size]. Inputs to this
    layer.  List index is towers.
* <b>`outputs_grads`</b>: List of Tensors, each of shape [batch_size, output_size],
    which are the gradients of the loss with respect to the layer's
    outputs. First index is source, second is tower.

* <b>`has_bias`</b>: bool. If True, append '1' to each input.

<h3 id="get_cholesky"><code>get_cholesky</code></h3>

``` python
get_cholesky(damping_func)
```



<h3 id="get_cholesky_inverse"><code>get_cholesky_inverse</code></h3>

``` python
get_cholesky_inverse(damping_func)
```



<h3 id="get_cov"><code>get_cov</code></h3>

``` python
get_cov()
```



<h3 id="get_cov_as_linear_operator"><code>get_cov_as_linear_operator</code></h3>

``` python
get_cov_as_linear_operator()
```



<h3 id="get_matpower"><code>get_matpower</code></h3>

``` python
get_matpower(
    exp,
    damping_func
)
```



<h3 id="instantiate_cov_variables"><code>instantiate_cov_variables</code></h3>

``` python
instantiate_cov_variables()
```

Makes the internal cov variable(s).

<h3 id="instantiate_inv_variables"><code>instantiate_inv_variables</code></h3>

``` python
instantiate_inv_variables()
```

Makes the internal "inverse" variable(s).

<h3 id="make_covariance_update_op"><code>make_covariance_update_op</code></h3>

``` python
make_covariance_update_op(ema_decay)
```

Constructs and returns the covariance update Op.

#### Args:

* <b>`ema_decay`</b>: The exponential moving average decay (float or Tensor).

#### Returns:

An Op for updating the covariance Variable referenced by _cov.

<h3 id="make_inverse_update_ops"><code>make_inverse_update_ops</code></h3>

``` python
make_inverse_update_ops()
```

Create and return update ops corresponding to registered computations.

<h3 id="register_cholesky"><code>register_cholesky</code></h3>

``` python
register_cholesky(damping_func)
```



<h3 id="register_cholesky_inverse"><code>register_cholesky_inverse</code></h3>

``` python
register_cholesky_inverse(damping_func)
```



<h3 id="register_matpower"><code>register_matpower</code></h3>

``` python
register_matpower(
    exp,
    damping_func
)
```





