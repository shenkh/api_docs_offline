<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.conj" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.conj

Returns the complex conjugate of a complex number.

### Aliases:

* `tf.compat.v1.conj`
* `tf.compat.v1.math.conj`
* `tf.compat.v2.math.conj`
* `tf.math.conj`

``` python
tf.math.conj(
    x,
    name=None
)
```



Defined in [`python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

<!-- Placeholder for "Used in" -->

Given a tensor `input` of complex numbers, this operation returns a tensor of
complex numbers that are the complex conjugate of each element in `input`. The
complex numbers in `input` must be of the form \\(a + bj\\), where *a* is the
real part and *b* is the imaginary part.

The complex conjugate returned by this operation is of the form \\(a - bj\\).

#### For example:


# tensor 'input' is [-2.25 + 4.75j, 3.25 + 5.75j]
tf.math.conj(input) ==> [-2.25 - 4.75j, 3.25 - 5.75j]


If `x` is real, it is returned unchanged.

#### Args:


* <b>`x`</b>: `Tensor` to conjugate.  Must have numeric or variant type.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` that is the conjugate of `x` (with the same type).



#### Raises:


* <b>`TypeError`</b>: If `x` is not a numeric tensor.