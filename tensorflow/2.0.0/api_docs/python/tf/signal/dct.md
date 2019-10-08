<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.signal.dct" />
<meta itemprop="path" content="Stable" />
</div>

# tf.signal.dct

``` python
tf.signal.dct(
    input,
    type=2,
    n=None,
    axis=-1,
    norm=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/signal/dct_ops.py`](/code/stable/tensorflow/python/ops/signal/dct_ops.py).

Computes the 1D [Discrete Cosine Transform (DCT)][dct] of `input`.

Currently only Types I, II and III are supported.
Type I is implemented using a length `2N` padded <a href="../../tf/signal/rfft.md"><code>tf.signal.rfft</code></a>.
Type II is implemented using a length `2N` padded <a href="../../tf/signal/rfft.md"><code>tf.signal.rfft</code></a>, as
described here: [Type 2 DCT using 2N FFT padded (Makhoul)](https://dsp.stackexchange.com/a/10606).
Type III is a fairly straightforward inverse of Type II
(i.e. using a length `2N` padded <a href="../../tf/signal/irfft.md"><code>tf.signal.irfft</code></a>).



#### Args:

* <b>`input`</b>: A `[..., samples]` `float32` `Tensor` containing the signals to
    take the DCT of.
* <b>`type`</b>: The DCT type to perform. Must be 1, 2 or 3.
* <b>`n`</b>: The length of the transform. If length is less than sequence length,
    only the first n elements of the sequence are considered for the DCT.
    If n is greater than the sequence length, zeros are padded and then
    the DCT is computed as usual.
* <b>`axis`</b>: For future expansion. The axis to compute the DCT along. Must be `-1`.
* <b>`norm`</b>: The normalization to apply. `None` for no normalization or `'ortho'`
    for orthonormal normalization.
* <b>`name`</b>: An optional name for the operation.


#### Returns:

A `[..., samples]` `float32` `Tensor` containing the DCT of `input`.


#### Raises:

* <b>`ValueError`</b>: If `type` is not `1`, `2` or `3`, `axis` is
    not `-1`, `n` is not `None` or greater than 0,
    or `norm` is not `None` or `'ortho'`.
* <b>`ValueError`</b>: If `type` is `1` and `norm` is `ortho`.

[dct]: https://en.wikipedia.org/wiki/Discrete_cosine_transform

#### Scipy Compatibility
Equivalent to [scipy.fftpack.dct](https://docs.scipy.org/doc/scipy-0.14.0/reference/generated/scipy.fftpack.dct.html)
 for Type-I, Type-II and Type-III DCT.

