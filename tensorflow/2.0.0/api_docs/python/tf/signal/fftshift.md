<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.signal.fftshift" />
<meta itemprop="path" content="Stable" />
</div>

# tf.signal.fftshift

``` python
tf.signal.fftshift(
    x,
    axes=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/signal/fft_ops.py`](/code/stable/tensorflow/python/ops/signal/fft_ops.py).

Shift the zero-frequency component to the center of the spectrum.

This function swaps half-spaces for all axes listed (defaults to all).
Note that ``y[0]`` is the Nyquist component only if ``len(x)`` is even.



For example:

```python
x = tf.signal.fftshift([ 0.,  1.,  2.,  3.,  4., -5., -4., -3., -2., -1.])
x.numpy() # array([-5., -4., -3., -2., -1.,  0.,  1.,  2.,  3.,  4.])
```

#### Args:

* <b>`x`</b>: `Tensor`, input tensor.
* <b>`axes`</b>: `int` or shape `tuple`, optional Axes over which to shift.  Default is
    None, which shifts all axes.
* <b>`name`</b>: An optional name for the operation.


#### Returns:

A `Tensor`, The shifted tensor.

#### Numpy Compatibility
Equivalent to numpy.fft.fftshift.
https://docs.scipy.org/doc/numpy/reference/generated/numpy.fft.fftshift.html

