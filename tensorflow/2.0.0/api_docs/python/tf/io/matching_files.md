<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.matching_files" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.matching_files

``` python
tf.io.matching_files(
    pattern,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_io_ops.py`.

Returns the set of files matching one or more glob patterns.

Note that this routine only supports wildcard characters in the
basename portion of the pattern, not in the directory portion.
Note also that the order of filenames returned is deterministic.

#### Args:

* <b>`pattern`</b>: A `Tensor` of type `string`.
    Shell wildcard pattern(s). Scalar or vector of type string.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `string`.