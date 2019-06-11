<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.strings.split" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.strings.split

Split elements of `input` based on `sep`.

``` python
tf.compat.v1.strings.split(
    input=None,
    sep=None,
    maxsplit=-1,
    result_type='SparseTensor',
    source=None,
    name=None
)
```



Defined in [`python/ops/ragged/ragged_string_ops.py`](/code/stable/tensorflow/python/ops/ragged/ragged_string_ops.py).

<!-- Placeholder for "Used in" -->

Let N be the size of `input` (typically N will be the batch size). Split each
element of `input` based on `sep` and return a `SparseTensor` or
`RaggedTensor` containing the split tokens. Empty tokens are ignored.

#### Examples:



```python
>>> tf.strings.split(['hello world', 'a b c'])
tf.SparseTensor(indices=[[0, 0], [0, 1], [1, 0], [1, 1], [1, 2]],
                values=['hello', 'world', 'a', 'b', 'c']
                dense_shape=[2, 3])

>>> tf.strings.split(['hello world', 'a b c'], result_type="RaggedTensor")
<tf.RaggedTensor [['hello', 'world'], ['a', 'b', 'c']]>
```

If `sep` is given, consecutive delimiters are not grouped together and are
deemed to delimit empty strings. For example, `input` of `"1<>2<><>3"` and
`sep` of `"<>"` returns `["1", "2", "", "3"]`. If `sep` is None or an empty
string, consecutive whitespace are regarded as a single separator, and the
result will contain no empty strings at the start or end if the string has
leading or trailing whitespace.

Note that the above mentioned behavior matches python's str.split.

#### Args:


* <b>`input`</b>: A string `Tensor` of rank `N`, the strings to split.  If
  `rank(input)` is not known statically, then it is assumed to be `1`.
* <b>`sep`</b>: `0-D` string `Tensor`, the delimiter character.
* <b>`maxsplit`</b>: An `int`. If `maxsplit > 0`, limit of the split of the result.
* <b>`result_type`</b>: The tensor type for the result: one of `"RaggedTensor"` or
  `"SparseTensor"`.
* <b>`source`</b>: alias for "input" argument.
* <b>`name`</b>: A name for the operation (optional).


#### Raises:


* <b>`ValueError`</b>: If sep is not a string.


#### Returns:

A `SparseTensor` or `RaggedTensor` of rank `N+1`, the strings split
according to the delimiter.
