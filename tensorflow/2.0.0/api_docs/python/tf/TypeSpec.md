<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.TypeSpec" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="value_type"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__ne__"/>
<meta itemprop="property" content="is_compatible_with"/>
<meta itemprop="property" content="most_specific_compatible_type"/>
</div>

# tf.TypeSpec

## Class `TypeSpec`





Defined in [`tensorflow/python/framework/type_spec.py`](/code/stable/tensorflow/python/framework/type_spec.py).

Specifies a TensorFlow value type.

A <a href="../tf/TypeSpec.md"><code>tf.TypeSpec</code></a> provides metadata describing an object accepted or returned
by TensorFlow APIs.  Concrete subclasses, such as <a href="../tf/TensorSpec.md"><code>tf.TensorSpec</code></a> and
<a href="../tf/RaggedTensorSpec.md"><code>tf.RaggedTensorSpec</code></a>, are used to describe different value types.

For example, <a href="../tf/function.md"><code>tf.function</code></a>'s `input_signature` argument accepts a list
(or nested structure) of `TypeSpec`s.

Creating new subclasses of TypeSpec (outside of TensorFlow core) is not
currently supported.  In particular, we may make breaking changes to the
private methods and properties defined by this base class.

## Properties

<h3 id="value_type"><code>value_type</code></h3>

The Python type for values that are compatible with this TypeSpec.



## Methods

<h3 id="__eq__"><code>__eq__</code></h3>

``` python
__eq__(other)
```

Return self==value.

<h3 id="__ne__"><code>__ne__</code></h3>

``` python
__ne__(other)
```

Return self!=value.

<h3 id="is_compatible_with"><code>is_compatible_with</code></h3>

``` python
is_compatible_with(spec_or_value)
```

Returns true if `spec_or_value` is compatible with this TypeSpec.

<h3 id="most_specific_compatible_type"><code>most_specific_compatible_type</code></h3>

``` python
most_specific_compatible_type(other)
```

Returns the most specific TypeSpec compatible with `self` and `other`.

#### Args:

* <b>`other`</b>: A `TypeSpec`.


#### Raises:

* <b>`ValueError`</b>: If there is no TypeSpec that is compatible with both `self`
    and `other`.



