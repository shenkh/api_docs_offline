<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.fisher_blocks.FullyConnectedKFACBasicFB" />
<meta itemprop="property" content="num_registered_towers"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="full_fisher_block"/>
<meta itemprop="property" content="instantiate_factors"/>
<meta itemprop="property" content="multiply"/>
<meta itemprop="property" content="multiply_cholesky"/>
<meta itemprop="property" content="multiply_cholesky_inverse"/>
<meta itemprop="property" content="multiply_inverse"/>
<meta itemprop="property" content="multiply_matpower"/>
<meta itemprop="property" content="register_additional_tower"/>
<meta itemprop="property" content="register_cholesky"/>
<meta itemprop="property" content="register_cholesky_inverse"/>
<meta itemprop="property" content="register_inverse"/>
<meta itemprop="property" content="register_matpower"/>
<meta itemprop="property" content="tensors_to_compute_grads"/>
</div>

# tf.contrib.kfac.fisher_blocks.FullyConnectedKFACBasicFB

## Class `FullyConnectedKFACBasicFB`

Inherits From: [`KroneckerProductFB`](../../../../tf/contrib/kfac/fisher_blocks/KroneckerProductFB.md)



Defined in [`tensorflow/contrib/kfac/python/ops/fisher_blocks.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/fisher_blocks.py).

K-FAC FisherBlock for fully-connected (dense) layers.

This uses the Kronecker-factorized approximation from the original
K-FAC paper (https://arxiv.org/abs/1503.05671)

## Properties

<h3 id="num_registered_towers"><code>num_registered_towers</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    layer_collection,
    has_bias=False
)
```

Creates a FullyConnectedKFACBasicFB block.

#### Args:

* <b>`layer_collection`</b>: The collection of all layers in the K-FAC approximate
      Fisher information matrix to which this FisherBlock belongs.
* <b>`has_bias`</b>: Whether the component Kronecker factors have an additive bias.
      (Default: False)

<h3 id="full_fisher_block"><code>full_fisher_block</code></h3>

``` python
full_fisher_block()
```

Explicitly constructs the full Fisher block.

Used for testing purposes. (In general, the result may be very large.)

#### Returns:

The full Fisher block.

<h3 id="instantiate_factors"><code>instantiate_factors</code></h3>

``` python
instantiate_factors(
    grads_list,
    damping
)
```

Instantiate Kronecker Factors for this FisherBlock.

#### Args:

* <b>`grads_list`</b>: List of list of Tensors. grads_list[i][j] is the
    gradient of the loss with respect to 'outputs' from source 'i' and
    tower 'j'. Each Tensor has shape [tower_minibatch_size, output_size].
* <b>`damping`</b>: 0-D Tensor or float. 'damping' * identity is approximately added
    to this FisherBlock's Fisher approximation.

<h3 id="multiply"><code>multiply</code></h3>

``` python
multiply(vector)
```

Multiplies the vector by the (damped) block.

#### Args:

* <b>`vector`</b>: The vector (a Tensor or tuple of Tensors) to be multiplied.


#### Returns:

The vector left-multiplied by the (damped) block.

<h3 id="multiply_cholesky"><code>multiply_cholesky</code></h3>

``` python
multiply_cholesky(
    vector,
    transpose=False
)
```

Multiplies the vector by the (damped) Cholesky-factor of the block.

#### Args:

* <b>`vector`</b>: The vector (a Tensor or tuple of Tensors) to be multiplied.
* <b>`transpose`</b>: Bool. If true the Cholesky factor is transposed before
    multiplying the vector. (Default: False)


#### Returns:

The vector left-multiplied by the (damped) Cholesky-factor of the block.

<h3 id="multiply_cholesky_inverse"><code>multiply_cholesky_inverse</code></h3>

``` python
multiply_cholesky_inverse(
    vector,
    transpose=False
)
```

Multiplies vector by the (damped) inverse Cholesky-factor of the block.

#### Args:

* <b>`vector`</b>: The vector (a Tensor or tuple of Tensors) to be multiplied.
* <b>`transpose`</b>: Bool. If true the Cholesky factor inverse is transposed
    before multiplying the vector. (Default: False)

#### Returns:

Vector left-multiplied by (damped) inverse Cholesky-factor of the block.

<h3 id="multiply_inverse"><code>multiply_inverse</code></h3>

``` python
multiply_inverse(vector)
```

Multiplies the vector by the (damped) inverse of the block.

#### Args:

* <b>`vector`</b>: The vector (a Tensor or tuple of Tensors) to be multiplied.


#### Returns:

The vector left-multiplied by the (damped) inverse of the block.

<h3 id="multiply_matpower"><code>multiply_matpower</code></h3>

``` python
multiply_matpower(
    vector,
    exp
)
```

Multiplies the vector by the (damped) matrix-power of the block.

#### Args:

* <b>`vector`</b>: The vector (a Tensor or tuple of Tensors) to be multiplied.
* <b>`exp`</b>: A float representing the power to raise the block by before
    multiplying it by the vector.


#### Returns:

The vector left-multiplied by the (damped) matrix-power of the block.

<h3 id="register_additional_tower"><code>register_additional_tower</code></h3>

``` python
register_additional_tower(
    inputs,
    outputs
)
```



<h3 id="register_cholesky"><code>register_cholesky</code></h3>

``` python
register_cholesky()
```

Registers a Cholesky factor to be computed by the block.

<h3 id="register_cholesky_inverse"><code>register_cholesky_inverse</code></h3>

``` python
register_cholesky_inverse()
```

Registers an inverse Cholesky factor to be computed by the block.

<h3 id="register_inverse"><code>register_inverse</code></h3>

``` python
register_inverse()
```

Registers a matrix inverse to be computed by the block.

<h3 id="register_matpower"><code>register_matpower</code></h3>

``` python
register_matpower(exp)
```

Registers a matrix power to be computed by the block.

#### Args:

* <b>`exp`</b>: A float representing the power to raise the block by.

<h3 id="tensors_to_compute_grads"><code>tensors_to_compute_grads</code></h3>

``` python
tensors_to_compute_grads()
```

Tensors to compute derivative of loss with respect to.



