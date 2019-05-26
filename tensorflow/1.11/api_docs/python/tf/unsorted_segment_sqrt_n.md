<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.unsorted_segment_sqrt_n" />
<meta itemprop="path" content="Stable" />
</div>

# tf.unsorted_segment_sqrt_n

``` python
tf.unsorted_segment_sqrt_n(
    data,
    segment_ids,
    num_segments,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

Computes the sum along segments of a tensor divided by the sqrt(N).

Read [the section on
segmentation](https://tensorflow.org/api_guides/python/math_ops#segmentation)
for an explanation of segments.

This operator is similar to the unsorted segment sum operator found
[here](../../../api_docs/python/math_ops.md#UnsortedSegmentSum).
Additionally to computing the sum over segments, it divides the results by
sqrt(N).

\\(output_i = 1/sqrt(N_i) \sum data_j\\) where the sum is over `j` such
that `segment_ids[j] == i` with \\N_i\\ being the number of occurrences
of id \\i\\.

If there is no entry for a given segment ID `i`, it outputs 0.

Note that this op only supports floating point and complex dtypes,
due to tf.sqrt only supporting these types.

segment_ids: A 1-D tensor whose rank is equal to the rank of `data`'s
first dimension.

output: Has same shape as data, except for dimension 0 which
has size `num_segments`.