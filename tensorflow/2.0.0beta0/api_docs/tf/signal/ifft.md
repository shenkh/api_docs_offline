<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.signal.ifft" />
<meta itemprop="path" content="Stable" />
</div>

# tf.signal.ifft

Inverse fast Fourier transform.

### Aliases:

* `tf.compat.v1.ifft`
* `tf.compat.v1.signal.ifft`
* `tf.compat.v1.spectral.ifft`
* `tf.compat.v2.signal.ifft`
* `tf.signal.ifft`

``` python
tf.signal.ifft(
    input,
    name=None
)
```



Defined in generated file: `python/ops/gen_spectral_ops.py`.

<!-- Placeholder for "Used in" -->

Computes the inverse 1-dimensional discrete Fourier transform over the
inner-most dimension of `input`.

#### Args:


* <b>`input`</b>: A `Tensor`. Must be one of the following types: `complex64`, `complex128`.
  A complex tensor.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.
