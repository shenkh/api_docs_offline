<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings.regex_replace" />
<meta itemprop="path" content="Stable" />
</div>

# tf.strings.regex_replace

``` python
tf.strings.regex_replace(
    input,
    pattern,
    rewrite,
    replace_global=True,
    name=None
)
```



Defined in [`tensorflow/python/ops/string_ops.py`](/code/stable/tensorflow/python/ops/string_ops.py).

Replace elements of `input` matching regex `pattern` with `rewrite`.

#### Args:

* <b>`input`</b>: string `Tensor`, the source strings to process.
* <b>`pattern`</b>: string or scalar string `Tensor`, regular expression to use,
    see more details at https://github.com/google/re2/wiki/Syntax
* <b>`rewrite`</b>: string or scalar string `Tensor`, value to use in match
    replacement, supports backslash-escaped digits (\1 to \9) can be to insert
    text matching corresponding parenthesized group.
* <b>`replace_global`</b>: `bool`, if `True` replace all non-overlapping matches,
    else replace only the first match.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

string `Tensor` of the same shape as `input` with specified replacements.