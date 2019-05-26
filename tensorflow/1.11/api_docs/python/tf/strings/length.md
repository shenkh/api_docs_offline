<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings.length" />
<meta itemprop="path" content="Stable" />
</div>

# tf.strings.length

``` python
tf.strings.length(
    input,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_string_ops.py`.

String lengths of `input`.

Computes the length of each string given in the input tensor.

#### Args:

* <b>`input`</b>: A `Tensor` of type `string`.
    The string for which to compute the length.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `int32`.