<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.unsorted_segment_min" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.unsorted_segment_min

### Aliases:

* `tf.math.unsorted_segment_min`
* `tf.unsorted_segment_min`

``` python
tf.math.unsorted_segment_min(
    data,
    segment_ids,
    num_segments,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Computes the minimum along segments of a tensor.

Read
[the section on segmentation](https://tensorflow.org/api_guides/python/math_ops#segmentation)
for an explanation of segments.

This operator is similar to the unsorted segment sum operator found
[(here)](../../../api_docs/python/math_ops.md#UnsortedSegmentSum).
Instead of computing the sum over segments, it computes the minimum such that:

\\(output_i = \min_j data_j\\) where min is over `j` such
that `segment_ids[j] == i`.

If the minimum is empty for a given segment ID `i`, it outputs the largest
possible value for the specific numeric type,
`output[i] = numeric_limits<T>::max()`.

#### Args:

* <b>`data`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `uint8`, `int16`, `int8`, `int64`, `bfloat16`, `uint16`, `half`, `uint32`, `uint64`.
* <b>`segment_ids`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
    A 1-D tensor whose rank is equal to the rank of `data`'s
    first dimension.
* <b>`num_segments`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `data`.