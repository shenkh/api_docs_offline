<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="bytes_or_text_types"/>
<meta itemprop="property" content="complex_types"/>
<meta itemprop="property" content="integral_types"/>
<meta itemprop="property" content="real_types"/>
</div>

# Module: tf.compat

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

[`as_bytes(...)`](../tf/compat/as_bytes.md): Converts `bytearray`, `bytes`, or unicode python input types to `bytes`.

[`as_str(...)`](../tf/compat/as_text.md): Converts any string-like python input types to unicode.

[`as_str_any(...)`](../tf/compat/as_str_any.md): Converts input to `str` type.

[`as_text(...)`](../tf/compat/as_text.md): Converts any string-like python input types to unicode.

[`dimension_at_index(...)`](../tf/compat/dimension_at_index.md): Compatibility utility required to allow for both V1 and V2 behavior in TF.

[`dimension_value(...)`](../tf/compat/dimension_value.md): Compatibility utility required to allow for both V1 and V2 behavior in TF.

[`forward_compatibility_horizon(...)`](../tf/compat/forward_compatibility_horizon.md): Context manager for testing forward compatibility of generated graphs.

[`forward_compatible(...)`](../tf/compat/forward_compatible.md): Return true if the forward compatibility window has expired.

[`path_to_str(...)`](../tf/compat/path_to_str.md): Converts input which is a `PathLike` object to `str` type.

## Other Members

<h3 id="bytes_or_text_types"><code>bytes_or_text_types</code></h3>

<h3 id="complex_types"><code>complex_types</code></h3>

<h3 id="integral_types"><code>integral_types</code></h3>

<h3 id="real_types"><code>real_types</code></h3>

