<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat" />
<meta itemprop="property" content="bytes_or_text_types"/>
<meta itemprop="property" content="complex_types"/>
<meta itemprop="property" content="integral_types"/>
<meta itemprop="property" content="real_types"/>
</div>

# Module: tf.compat



Defined in [`tensorflow/compat/__init__.py`](https://www.tensorflow.org/code/tensorflow/compat/__init__.py).

Functions for Python 2 vs. 3 compatibility.

## Conversion routines
In addition to the functions below, `as_str` converts an object to a `str`.


## Types
The compatibility module also provides the following types:

* `bytes_or_text_types`
* `complex_types`
* `integral_types`
* `real_types`

## Functions

[`as_bytes(...)`](../tf/compat/as_bytes.md): Converts either bytes or unicode to `bytes`, using utf-8 encoding for text.

[`as_str(...)`](../tf/compat/as_str.md): Returns the given argument as a unicode string.

[`as_str_any(...)`](../tf/compat/as_str_any.md): Converts to `str` as `str(value)`, but use `as_str` for `bytes`.

[`as_text(...)`](../tf/compat/as_str.md): Returns the given argument as a unicode string.

[`path_to_str(...)`](../tf/compat/path_to_str.md): Returns the file system path representation of a `PathLike` object, else as it is.

## Other Members

`bytes_or_text_types`

`complex_types`

`integral_types`

`real_types`

