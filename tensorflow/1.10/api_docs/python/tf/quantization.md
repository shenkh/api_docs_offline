<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.quantization" />
</div>

# Module: tf.quantization



Defined in [`tensorflow/quantization/__init__.py`](https://www.tensorflow.org/code/tensorflow/quantization/__init__.py).

Public API for tf.quantization namespace.

## Functions

[`dequantize(...)`](../tf/dequantize.md): Dequantize the 'input' tensor into a float Tensor.

[`fake_quant_with_min_max_args(...)`](../tf/fake_quant_with_min_max_args.md): Fake-quantize the 'inputs' tensor, type float to 'outputs' tensor of same type.

[`fake_quant_with_min_max_args_gradient(...)`](../tf/fake_quant_with_min_max_args_gradient.md): Compute gradients for a FakeQuantWithMinMaxArgs operation.

[`fake_quant_with_min_max_vars(...)`](../tf/fake_quant_with_min_max_vars.md): Fake-quantize the 'inputs' tensor of type float via global float scalars `min`

[`fake_quant_with_min_max_vars_gradient(...)`](../tf/fake_quant_with_min_max_vars_gradient.md): Compute gradients for a FakeQuantWithMinMaxVars operation.

[`fake_quant_with_min_max_vars_per_channel(...)`](../tf/fake_quant_with_min_max_vars_per_channel.md): Fake-quantize the 'inputs' tensor of type float and one of the shapes: `[d]`,

[`fake_quant_with_min_max_vars_per_channel_gradient(...)`](../tf/fake_quant_with_min_max_vars_per_channel_gradient.md): Compute gradients for a FakeQuantWithMinMaxVarsPerChannel operation.

[`quantized_concat(...)`](../tf/quantized_concat.md): Concatenates quantized tensors along one dimension.

