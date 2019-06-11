<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.string_split" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.string_split

Split elements of `source` based on `delimiter`. (deprecated arguments)

``` python
tf.compat.v1.string_split(
    source,
    sep=None,
    skip_empty=True,
    delimiter=None,
    result_type='SparseTensor',
    name=None
)
```



Defined in [`python/ops/ragged/ragged_string_ops.py`](/code/stable/tensorflow/python/ops/ragged/ragged_string_ops.py).

<!-- Placeholder for "Used in" -->

Warning: SOME ARGUMENTS ARE DEPRECATED: `(delimiter)`. They will be removed in a future version.
Instructions for updating:
delimiter is deprecated, please use sep instead.

Let N be the size of `source` (typically N will be the batch size). Split each
element of `source` based on `delimiter` and return a `SparseTensor`
or `RaggedTensor` containing the split tokens. Empty tokens are ignored.

If `sep` is an empty string, each element of the `source` is split
into individual strings, each containing one byte. (This includes splitting
multibyte sequences of UTF-8.) If delimiter contains multiple bytes, it is
treated as a set of delimiters with each considered a potential split point.

#### Examples:



```python
>>> tf.strings.split(['hello world', 'a b c'])
tf.SparseTensor(indices=[[0, 0], [0, 1], [1, 0], [1, 1], [1, 2]],
                values=['hello', 'world', 'a', 'b', 'c']
                dense_shape=[2, 3])

>>> tf.strings.split(['hello world', 'a b c'], result_type="RaggedTensor")
<tf.RaggedTensor [['hello', 'world'], ['a', 'b', 'c']]>
```

#### Args:


* <b>`source`</b>: `1-D` string `Tensor`, the strings to split.
* <b>`sep`</b>: `0-D` string `Tensor`, the delimiter character, the string should
  be length 0 or 1. Default is ' '.
* <b>`skip_empty`</b>: A `bool`. If `True`, skip the empty strings from the result.
* <b>`delimiter`</b>: deprecated alias for `sep`.
* <b>`result_type`</b>: The tensor type for the result: one of `"RaggedTensor"` or
  `"SparseTensor"`.
* <b>`name`</b>: A name for the operation (optional).


#### Raises:


* <b>`ValueError`</b>: If delimiter is not a string.


#### Returns:

A `SparseTensor` or `RaggedTensor` of rank `2`, the strings split according
to the delimiter.  The first column of the indices corresponds to the row
in `source` and the second column corresponds to the index of the split
component in this row.
