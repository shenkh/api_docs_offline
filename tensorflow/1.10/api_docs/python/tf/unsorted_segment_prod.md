<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.unsorted_segment_prod" />
</div>

# tf.unsorted_segment_prod

### Aliases:

* `tf.math.unsorted_segment_prod`
* `tf.unsorted_segment_prod`

``` python
tf.unsorted_segment_prod(
    data,
    segment_ids,
    num_segments,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Computes the product along segments of a tensor.

Read <a href="../../../api_guides/python/math_ops.md#segmentation">the section on segmentation</a> for an explanation of
segments.

This operator is similar to the unsorted segment sum operator found
[(here)](../../../api_docs/python/math_ops.md#UnsortedSegmentSum).
Instead of computing the sum over segments, it computes the product of all
entries belonging to a segment such that:

\\(output_i = \prod_j data_j\\) where the product is over `j` such
that `segment_ids[j] == i`.

If there is no entry for a given segment ID `i`, it outputs 1.

#### Args:

* <b>`data`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `uint8`, `int16`, `int8`, `complex64`, `int64`, `qint8`, `quint8`, `qint32`, `bfloat16`, `uint16`, `complex128`, `half`, `uint32`, `uint64`.
* <b>`segment_ids`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
    A 1-D tensor whose rank is equal to the rank of `data`'s
    first dimension.
* <b>`num_segments`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `data`.