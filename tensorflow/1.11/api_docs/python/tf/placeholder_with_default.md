<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.placeholder_with_default" />
<meta itemprop="path" content="Stable" />
</div>

# tf.placeholder_with_default

``` python
tf.placeholder_with_default(
    input,
    shape,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_array_ops.py`.

See the guide: [Inputs and Readers > Placeholders](../../../api_guides/python/io_ops.md#Placeholders)

A placeholder op that passes through `input` when its output is not fed.

#### Args:

* <b>`input`</b>: A `Tensor`. The default value to produce when `output` is not fed.
* <b>`shape`</b>: A <a href="../tf/TensorShape.md"><code>tf.TensorShape</code></a> or list of `ints`.
    The (possibly partial) shape of the tensor.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.