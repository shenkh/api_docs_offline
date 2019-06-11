<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.quantization.fake_quant_with_min_max_vars_per_channel" />
<meta itemprop="path" content="Stable" />
</div>

# tf.quantization.fake_quant_with_min_max_vars_per_channel

Fake-quantize the 'inputs' tensor of type float and one of the shapes: `[d]`,

### Aliases:

* `tf.compat.v1.fake_quant_with_min_max_vars_per_channel`
* `tf.compat.v1.quantization.fake_quant_with_min_max_vars_per_channel`
* `tf.compat.v2.quantization.fake_quant_with_min_max_vars_per_channel`
* `tf.quantization.fake_quant_with_min_max_vars_per_channel`

``` python
tf.quantization.fake_quant_with_min_max_vars_per_channel(
    inputs,
    min,
    max,
    num_bits=8,
    narrow_range=False,
    name=None
)
```



Defined in generated file: `python/ops/gen_array_ops.py`.

<!-- Placeholder for "Used in" -->

`[b, d]` `[b, h, w, d]` via per-channel floats `min` and `max` of shape `[d]`
to 'outputs' tensor of same shape as `inputs`.

`[min; max]` define the clamping range for the `inputs` data.
`inputs` values are quantized into the quantization range (`[0; 2^num_bits - 1]`
when `narrow_range` is false and `[1; 2^num_bits - 1]` when it is true) and
then de-quantized and output as floats in `[min; max]` interval.
`num_bits` is the bitwidth of the quantization; between 2 and 16, inclusive.

Before quantization, `min` and `max` values are adjusted with the following
logic.
It is suggested to have `min <= 0 <= max`. If `0` is not in the range of values,
the behavior can be unexpected:
If `0 < min < max`: `min_adj = 0` and `max_adj = max - min`.
If `min < max < 0`: `min_adj = min - max` and `max_adj = 0`.
If `min <= 0 <= max`: `scale = (max - min) / (2^num_bits - 1) `,
`min_adj = scale * round(min / scale)` and `max_adj = max + min_adj - min`.

This operation has a gradient and thus allows for training `min` and `max`
values.

#### Args:


* <b>`inputs`</b>: A `Tensor` of type `float32`.
* <b>`min`</b>: A `Tensor` of type `float32`.
* <b>`max`</b>: A `Tensor` of type `float32`.
* <b>`num_bits`</b>: An optional `int`. Defaults to `8`.
* <b>`narrow_range`</b>: An optional `bool`. Defaults to `False`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `float32`.
