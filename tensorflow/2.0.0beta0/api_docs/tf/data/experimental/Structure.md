<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.Structure" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__ne__"/>
<meta itemprop="property" content="from_value"/>
<meta itemprop="property" content="is_compatible_with"/>
</div>

# tf.data.experimental.Structure

## Class `Structure`

Represents structural information, such as type and shape, about a value.



### Aliases:

* Class `tf.compat.v1.data.experimental.Structure`
* Class `tf.compat.v2.data.experimental.Structure`
* Class `tf.data.experimental.Structure`



Defined in [`python/data/util/structure.py`](/code/stable/tensorflow/python/data/util/structure.py).

<!-- Placeholder for "Used in" -->

A `Structure` generalizes the <a href="../../../tf/Tensor.md#dtype"><code>tf.Tensor.dtype</code></a> and <a href="../../../tf/Tensor.md#shape"><code>tf.Tensor.shape</code></a>
properties, so that we can define generic containers of objects including:

* <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>
* <a href="../../../tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a>
* Nested structures of the above.

TODO(b/110122868): In the future, a single `Structure` will replace the
`tf.data.Dataset.output_types`, `tf.data.Dataset.output_shapes`,
and `tf.data.Dataset.output_classes`, and similar properties and arguments in
the <a href="../../../tf/compat/v1/data/Iterator.md"><code>tf.compat.v1.data.Iterator</code></a> and `Optional` classes.

## Methods

<h3 id="__eq__"><code>__eq__</code></h3>

``` python
__eq__(other)
```

Returns the this structure and the input structure are equal.


#### Args:


* <b>`other`</b>: the structure to use for equality check


#### Returns:

`True` if this and the input structure are equal and `False` otherwise.


<h3 id="__ne__"><code>__ne__</code></h3>

``` python
__ne__(other)
```

Return self!=value.


<h3 id="from_value"><code>from_value</code></h3>

``` python
@staticmethod
from_value(value)
```

Returns a `Structure` that represents the given `value`.


#### Args:


* <b>`value`</b>: A potentially structured value.


#### Returns:

A `Structure` that is compatible with `value`.



#### Raises:


* <b>`TypeError`</b>: If a structure cannot be built for `value`, because its type
  or one of its component types is not supported.

<h3 id="is_compatible_with"><code>is_compatible_with</code></h3>

``` python
is_compatible_with(other)
```

Returns `True` if `other` is compatible with this structure.

A structure `t` is a "subtype" of `s` if:

* `s` and `t` are instances of the same `Structure` subclass.
* The nested structures (if any) of `s` and `t` are the same, according to
  <a href="../../../tf/nest/assert_same_structure.md"><code>tf.nest.assert_same_structure</code></a>, and each nested
  structure of `t` is a "subtype" of the corresponding nested structure of
  `s`.
* Any <a href="../../../tf/dtypes/DType.md"><code>tf.DType</code></a> components of `t` are the same as the corresponding
  components in `s`.
* Any <a href="../../../tf/TensorShape.md"><code>tf.TensorShape</code></a> components of `t` are compatible with the
  corresponding components in `s`, according to
  <a href="../../../tf/TensorShape.md#is_compatible_with"><code>tf.TensorShape.is_compatible_with</code></a>.

#### Args:


* <b>`other`</b>: A `Structure`.


#### Returns:

`True` if `other` is a subtype of this structure, otherwise `False`.




