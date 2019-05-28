<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.ifft3d" />
</div>

# tf.ifft3d

### Aliases:

* `tf.ifft3d`
* `tf.spectral.ifft3d`

``` python
tf.ifft3d(
    input,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_spectral_ops.py`.

See the guide: [Spectral Functions > Discrete Fourier Transforms](../../../api_guides/python/spectral_ops.md#Discrete_Fourier_Transforms)

Inverse 3D fast Fourier transform.

Computes the inverse 3-dimensional discrete Fourier transform over the
inner-most 3 dimensions of `input`.

#### Args:

* <b>`input`</b>: A `Tensor`. Must be one of the following types: `complex64`, `complex128`.
    A complex64 tensor.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.