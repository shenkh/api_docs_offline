<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.unsorted_segment_prod" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.unsorted_segment_prod

Computes the product along segments of a tensor.

### Aliases:

* `tf.compat.v1.math.unsorted_segment_prod`
* `tf.compat.v1.unsorted_segment_prod`
* `tf.compat.v2.math.unsorted_segment_prod`
* `tf.math.unsorted_segment_prod`

``` python
tf.math.unsorted_segment_prod(
    data,
    segment_ids,
    num_segments,
    name=None
)
```



Defined in generated file: `python/ops/gen_math_ops.py`.

<!-- Placeholder for "Used in" -->

Read
[the section on segmentation](https://tensorflow.org/api_docs/python/tf/math#Segmentation)
for an explanation of segments.

This operator is similar to the unsorted segment sum operator found
[(here)](../../../api_docs/python/math_ops.md#UnsortedSegmentSum).
Instead of computing the sum over segments, it computes the product of all
entries belonging to a segment such that:

\\(output_i = \prod_{j...} data[j...]\\) where the product is over tuples
`j...` such that `segment_ids[j...] == i`.

#### For example:



``` python
c = tf.constant([[1,2,3,4], [5,6,7,8], [4,3,2,1]])
tf.unsorted_segment_prod(c, tf.constant([0, 1, 0]), num_segments=2)
# ==> [[ 4,  6, 6, 4],
#       [5,  6, 7, 8]]
```

If there is no entry for a given segment ID `i`, it outputs 1.

If the given segment ID `i` is negative, then the corresponding value is
dropped, and will not be included in the result.

#### Args:


* <b>`data`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `uint8`, `int16`, `int8`, `complex64`, `int64`, `qint8`, `quint8`, `qint32`, `bfloat16`, `uint16`, `complex128`, `half`, `uint32`, `uint64`.
* <b>`segment_ids`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
  A tensor whose shape is a prefix of `data.shape`.
* <b>`num_segments`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `data`.
