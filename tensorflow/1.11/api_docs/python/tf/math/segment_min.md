<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.segment_min" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.segment_min

### Aliases:

* `tf.math.segment_min`
* `tf.segment_min`

``` python
tf.math.segment_min(
    data,
    segment_ids,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

See the guide: [Math > Segmentation](../../../../api_guides/python/math_ops.md#Segmentation)

Computes the minimum along segments of a tensor.

Read
[the section on segmentation](https://tensorflow.org/api_guides/python/math_ops#Segmentation)
for an explanation of segments.

Computes a tensor such that
\\(output_i = \min_j(data_j)\\) where `min` is over `j` such
that `segment_ids[j] == i`.

If the min is empty for a given segment ID `i`, `output[i] = 0`.

<div style="width:70%; margin:auto; margin-bottom:10px; margin-top:20px;">
<img style="width:100%" src="https://www.tensorflow.org/images/SegmentMin.png" alt>
</div>

#### Args:

* <b>`data`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `uint8`, `int16`, `int8`, `int64`, `bfloat16`, `uint16`, `half`, `uint32`, `uint64`.
* <b>`segment_ids`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
    A 1-D tensor whose rank is equal to the rank of `data`'s
    first dimension.  Values should be sorted and can be repeated.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `data`.