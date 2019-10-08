<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.signal.rfft3d" />
<meta itemprop="path" content="Stable" />
</div>

# tf.signal.rfft3d

``` python
tf.signal.rfft3d(
    input_tensor,
    fft_length=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/signal/fft_ops.py`](/code/stable/tensorflow/python/ops/signal/fft_ops.py).

3D real-valued fast Fourier transform.

Computes the 3-dimensional discrete Fourier transform of a real-valued signal
over the inner-most 3 dimensions of `input`.

Since the DFT of a real signal is Hermitian-symmetric, `RFFT3D` only returns the
`fft_length / 2 + 1` unique components of the FFT for the inner-most dimension
of `output`: the zero-frequency term, followed by the `fft_length / 2`
positive-frequency terms.

Along each axis `RFFT3D` is computed on, if `fft_length` is smaller than the
corresponding dimension of `input`, the dimension is cropped. If it is larger,
the dimension is padded with zeros.

#### Args:

* <b>`input`</b>: A `Tensor` of type `float32`. A float32 tensor.
* <b>`fft_length`</b>: A `Tensor` of type `int32`.
    An int32 tensor of shape [3]. The FFT length for each dimension.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `complex64`.