<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings.unicode_split_with_offsets" />
<meta itemprop="path" content="Stable" />
</div>

# tf.strings.unicode_split_with_offsets

``` python
tf.strings.unicode_split_with_offsets(
    input,
    input_encoding,
    errors='replace',
    replacement_char=65533,
    name=None
)
```



Defined in [`tensorflow/python/ops/ragged/ragged_string_ops.py`](/code/stable/tensorflow/python/ops/ragged/ragged_string_ops.py).

Splits each string into a sequence of code points with start offsets.

This op is similar to `tf.strings.decode(...)`, but it also returns the
start offset for each character in its respective string.  This information
can be used to align the characters with the original byte sequence.

Returns a tuple `(chars, start_offsets)` where:

* `chars[i1...iN, j]` is the substring of `input[i1...iN]` that encodes its
  `j`th character, when decoded using `input_encoding`.
* `start_offsets[i1...iN, j]` is the start byte offset for the `j`th
  character in `input[i1...iN]`, when decoded using `input_encoding`.

#### Args:

* <b>`input`</b>: An `N` dimensional potentially ragged `string` tensor with shape
    `[D1...DN]`.  `N` must be statically known.
* <b>`input_encoding`</b>: String name for the unicode encoding that should be used to
    decode each string.
* <b>`errors`</b>: Specifies the response when an input string can't be converted
    using the indicated encoding. One of:
    * `'strict'`: Raise an exception for any illegal substrings.
    * `'replace'`: Replace illegal substrings with `replacement_char`.
    * `'ignore'`: Skip illegal substrings.
* <b>`replacement_char`</b>: The replacement codepoint to be used in place of invalid
    substrings in `input` when `errors='replace'`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

  A tuple of `N+1` dimensional tensors `(codepoints, start_offsets)`.

  * `codepoints` is an `int32` tensor with shape `[D1...DN, (num_chars)]`.
  * `offsets` is an `int64` tensor with shape `[D1...DN, (num_chars)]`.

  The returned tensors are <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a>s if `input` is a scalar, or
  <a href="../../tf/RaggedTensor.md"><code>tf.RaggedTensor</code></a>s otherwise.

#### Example:
  ```python
  >>> input = [s.encode('utf8') for s in (u'G\xf6\xf6dnight', u'\U0001f60a')]
  >>> result = tf.strings.unicode_split_with_offsets(input, 'UTF-8')
  >>> result[0].tolist()  # character substrings
  [['G', '\xc3\xb6', '\xc3\xb6', 'd', 'n', 'i', 'g', 'h', 't'],
   ['\xf0\x9f\x98\x8a']]
  >>> result[1].tolist()  # offsets
 [[0, 1, 3, 5, 6, 7, 8, 9, 10], [0]]
  ```