<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.fisher_blocks.ConvKFCBasicFB" />
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

# tf.contrib.kfac.fisher_blocks.ConvKFCBasicFB

## Class `ConvKFCBasicFB`

Inherits From: [`KroneckerProductFB`](../../../../tf/contrib/kfac/fisher_blocks/KroneckerProductFB.md)



Defined in [`tensorflow/contrib/kfac/python/ops/fisher_blocks.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/fisher_blocks.py).

FisherBlock for convolutional layers using the basic KFC approx.

Estimates the Fisher Information matrix's blog for a convolutional
layer.

Consider a convoluational layer in this model with (unshared) filter matrix
'w'. For a minibatch that produces inputs 'a' and output preactivations 's',
this FisherBlock estimates,

  $$F(w) = \#locations * kronecker(E[flat(a) flat(a)^T],
                                E[flat(ds) flat(ds)^T])$$

where

  $$ds = (d / ds) log p(y | x, w)$$
  #locations = number of (x, y) locations where 'w' is applied.

where the expectation is taken over all examples and locations and flat()
concatenates an array's leading dimensions.

See equation 23 in https://arxiv.org/abs/1602.01407 for details.

## Properties

<h3 id="num_registered_towers"><code>num_registered_towers</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    layer_collection,
    params,
    padding,
    strides=None,
    dilation_rate=None,
    data_format=None,
    extract_patches_fn=None
)
```

Creates a ConvKFCBasicFB block.

#### Args:

* <b>`layer_collection`</b>: The collection of all layers in the K-FAC approximate
      Fisher information matrix to which this FisherBlock belongs.
* <b>`params`</b>: The parameters (Tensor or tuple of Tensors) of this layer. If
    kernel alone, a Tensor of shape [..spatial_filter_shape..,
    in_channels, out_channels]. If kernel and bias, a tuple of 2 elements
    containing the previous and a Tensor of shape [out_channels].
* <b>`padding`</b>: str. Padding method.
* <b>`strides`</b>: List of ints or None. Contains [..spatial_filter_strides..] if
    'extract_patches_fn' is compatible with tf.nn.convolution(), else
    [1, ..spatial_filter_strides, 1].
* <b>`dilation_rate`</b>: List of ints or None. Rate for dilation along each spatial
    dimension if 'extract_patches_fn' is compatible with
    tf.nn.convolution(), else [1, ..spatial_dilation_rates.., 1].
* <b>`data_format`</b>: str or None. Format of input data.
* <b>`extract_patches_fn`</b>: str or None. Name of function that extracts image
    patches. One of "extract_convolution_patches", "extract_image_patches",
    "extract_pointwise_conv2d_patches".

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

Creates and registers the component factors of this Fisher block.

#### Args:

* <b>`grads_list`</b>: A list gradients (each a Tensor or tuple of Tensors) with
      respect to the tensors returned by tensors_to_compute_grads() that
      are to be used to estimate the block.
* <b>`damping`</b>: The damping factor (float or Tensor).

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



