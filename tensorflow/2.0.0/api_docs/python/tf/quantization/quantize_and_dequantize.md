<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.quantization.quantize_and_dequantize" />
<meta itemprop="path" content="Stable" />
</div>

# tf.quantization.quantize_and_dequantize

``` python
tf.quantization.quantize_and_dequantize(
    input,
    input_min,
    input_max,
    signed_input=True,
    num_bits=8,
    range_given=False,
    round_mode='HALF_TO_EVEN',
    name=None,
    narrow_range=False
)
```



Defined in [`tensorflow/python/ops/array_ops.py`](/code/stable/tensorflow/python/ops/array_ops.py).

Quantizes then dequantizes a tensor.

#### Args:

* <b>`input`</b>: A `Tensor` to quantize and dequantize.
* <b>`input_min`</b>: If range_given=True, the minimum input value that needs to be
    represented in the quantized representation.
* <b>`input_max`</b>: If range_given=True, the maximum input value that needs to be
    represented in the quantized representation.
* <b>`signed_input`</b>: True if the quantization is signed or unsigned.
* <b>`num_bits`</b>: The bitwidth of the quantization.
* <b>`range_given`</b>: If true use `input_min` and `input_max` for the range of the
    input, otherwise determine min and max from the input `Tensor`.
* <b>`round_mode`</b>: Rounding mode when rounding from float values to quantized ones.
* <b>`name`</b>: Optional name for the operation.
* <b>`narrow_range`</b>: If true, then the absolute value of the quantized minimum
    value is the same as the quantized maximum value, instead of 1 greater.
    i.e. for 8 bit quantization, the minimum value is -127 instead of -128.


#### Returns:

A `Tensor`. Each element is the result of quantizing and dequantizing the
corresponding element of `input`.