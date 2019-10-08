<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.signal.idct" />
<meta itemprop="path" content="Stable" />
</div>

# tf.signal.idct

``` python
tf.signal.idct(
    input,
    type=2,
    n=None,
    axis=-1,
    norm=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/signal/dct_ops.py`](/code/stable/tensorflow/python/ops/signal/dct_ops.py).

Computes the 1D [Inverse Discrete Cosine Transform (DCT)][idct] of `input`.

Currently only Types I, II and III are supported. Type III is the inverse of
Type II, and vice versa.

Note that you must re-normalize by 1/(2n) to obtain an inverse if `norm` is
not `'ortho'`. That is:
`signal == idct(dct(signal)) * 0.5 / signal.shape[-1]`.
When `norm='ortho'`, we have:
`signal == idct(dct(signal, norm='ortho'), norm='ortho')`.



#### Args:

* <b>`input`</b>: A `[..., samples]` `float32` `Tensor` containing the signals to take
    the DCT of.
* <b>`type`</b>: The IDCT type to perform. Must be 1, 2 or 3.
* <b>`n`</b>: For future expansion. The length of the transform. Must be `None`.
* <b>`axis`</b>: For future expansion. The axis to compute the DCT along. Must be `-1`.
* <b>`norm`</b>: The normalization to apply. `None` for no normalization or `'ortho'`
    for orthonormal normalization.
* <b>`name`</b>: An optional name for the operation.


#### Returns:

A `[..., samples]` `float32` `Tensor` containing the IDCT of `input`.


#### Raises:

* <b>`ValueError`</b>: If `type` is not `1`, `2` or `3`, `n` is not `None, `axis` is
    not `-1`, or `norm` is not `None` or `'ortho'`.

[idct]:
https://en.wikipedia.org/wiki/Discrete_cosine_transform#Inverse_transforms

#### Scipy Compatibility
Equivalent to [scipy.fftpack.idct](https://docs.scipy.org/doc/scipy-0.14.0/reference/generated/scipy.fftpack.idct.html)
 for Type-I, Type-II and Type-III DCT.

