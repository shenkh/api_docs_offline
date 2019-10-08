<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.signal.ifftshift" />
<meta itemprop="path" content="Stable" />
</div>

# tf.signal.ifftshift

``` python
tf.signal.ifftshift(
    x,
    axes=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/signal/fft_ops.py`](/code/stable/tensorflow/python/ops/signal/fft_ops.py).

The inverse of fftshift.

Although identical for even-length x,
the functions differ by one sample for odd-length x.



For example:

```python
x = tf.signal.ifftshift([[ 0.,  1.,  2.],[ 3.,  4., -4.],[-3., -2., -1.]])
x.numpy() # array([[ 4., -4.,  3.],[-2., -1., -3.],[ 1.,  2.,  0.]])
```

#### Args:

* <b>`x`</b>: `Tensor`, input tensor.
* <b>`axes`</b>: `int` or shape `tuple` Axes over which to calculate. Defaults to None,
    which shifts all axes.
* <b>`name`</b>: An optional name for the operation.


#### Returns:

A `Tensor`, The shifted tensor.

#### Numpy Compatibility
Equivalent to numpy.fft.ifftshift.
https://docs.scipy.org/doc/numpy/reference/generated/numpy.fft.ifftshift.html

