<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.signal.fft2d" />
<meta itemprop="path" content="Stable" />
</div>

# tf.signal.fft2d

``` python
tf.signal.fft2d(
    input,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_spectral_ops.py`.

2D fast Fourier transform.

Computes the 2-dimensional discrete Fourier transform over the inner-most
2 dimensions of `input`.

#### Args:

* <b>`input`</b>: A `Tensor`. Must be one of the following types: `complex64`, `complex128`.
    A complex tensor.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.