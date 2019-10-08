<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.signal.hamming_window" />
<meta itemprop="path" content="Stable" />
</div>

# tf.signal.hamming_window

``` python
tf.signal.hamming_window(
    window_length,
    periodic=True,
    dtype=tf.dtypes.float32,
    name=None
)
```



Defined in [`tensorflow/python/ops/signal/window_ops.py`](/code/stable/tensorflow/python/ops/signal/window_ops.py).

Generate a [Hamming][hamming] window.

#### Args:

* <b>`window_length`</b>: A scalar `Tensor` indicating the window length to generate.
* <b>`periodic`</b>: A bool `Tensor` indicating whether to generate a periodic or
    symmetric window. Periodic windows are typically used for spectral
    analysis while symmetric windows are typically used for digital
    filter design.
* <b>`dtype`</b>: The data type to produce. Must be a floating point type.
* <b>`name`</b>: An optional name for the operation.


#### Returns:

A `Tensor` of shape `[window_length]` of type `dtype`.


#### Raises:

* <b>`ValueError`</b>: If `dtype` is not a floating point type.

[hamming]: https://en.wikipedia.org/wiki/Window_function#Hann_and_Hamming_windows