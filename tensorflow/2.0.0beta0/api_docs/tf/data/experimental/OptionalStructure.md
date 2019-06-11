<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.OptionalStructure" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__ne__"/>
<meta itemprop="property" content="from_value"/>
<meta itemprop="property" content="is_compatible_with"/>
</div>

# tf.data.experimental.OptionalStructure

## Class `OptionalStructure`

Represents an optional potentially containing a structured value.

Inherits From: [`Structure`](../../../tf/data/experimental/Structure.md)

### Aliases:

* Class `tf.compat.v1.data.experimental.OptionalStructure`
* Class `tf.compat.v2.data.experimental.OptionalStructure`
* Class `tf.data.experimental.OptionalStructure`



Defined in [`python/data/ops/optional_ops.py`](/code/stable/tensorflow/python/data/ops/optional_ops.py).

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(value_structure)
```

Initialize self.  See help(type(self)) for accurate signature.




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




