<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings" />
</div>

# Module: tf.strings



Defined in [`tensorflow/strings/__init__.py`](https://www.tensorflow.org/code/tensorflow/strings/__init__.py).

Operations for working with string Tensors.

See the <a href="../../../api_guides/python/string_ops.md">Strings</a> guide.

## Functions

[`join(...)`](../tf/string_join.md): Joins the strings in the given list of string tensors into one tensor;

[`regex_full_match(...)`](../tf/strings/regex_full_match.md): Check if the input matches the regex pattern.

[`regex_replace(...)`](../tf/regex_replace.md): Replaces the match of pattern in input with rewrite.

[`split(...)`](../tf/strings/split.md): Split elements of `source` based on `sep` into a `SparseTensor`.

[`strip(...)`](../tf/string_strip.md): Strip leading and trailing whitespaces from the Tensor.

[`substr(...)`](../tf/substr.md): Return substrings from `Tensor` of strings.

[`to_hash_bucket(...)`](../tf/string_to_hash_bucket.md): Converts each string in the input Tensor to its hash mod by a number of buckets.

[`to_hash_bucket_fast(...)`](../tf/string_to_hash_bucket_fast.md): Converts each string in the input Tensor to its hash mod by a number of buckets.

[`to_hash_bucket_strong(...)`](../tf/string_to_hash_bucket_strong.md): Converts each string in the input Tensor to its hash mod by a number of buckets.

[`to_number(...)`](../tf/string_to_number.md): Converts each string in the input Tensor to the specified numeric type.

