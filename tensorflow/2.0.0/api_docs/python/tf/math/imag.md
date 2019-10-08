<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.imag" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.imag

``` python
tf.math.imag(
    input,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

Returns the imaginary part of a complex (or real) tensor.

Given a tensor `input`, this operation returns a tensor of type `float` that
is the imaginary part of each element in `input` considered as a complex
number. If `input` is real, a tensor of all zeros is returned.

For example:

```python
x = tf.constant([-2.25 + 4.75j, 3.25 + 5.75j])
tf.math.imag(x)  # [4.75, 5.75]
```

#### Args:

* <b>`input`</b>: A `Tensor`. Must be one of the following types: `float`, `double`,
    `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `float32` or `float64`.