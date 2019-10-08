<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.IndexedSlicesSpec" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="value_type"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__ne__"/>
<meta itemprop="property" content="is_compatible_with"/>
<meta itemprop="property" content="most_specific_compatible_type"/>
</div>

# tf.IndexedSlicesSpec

## Class `IndexedSlicesSpec`

Inherits From: [`TypeSpec`](../tf/TypeSpec.md)



Defined in [`tensorflow/python/framework/indexed_slices.py`](/code/stable/tensorflow/python/framework/indexed_slices.py).

Type specification for a <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a>.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    shape=None,
    dtype=tf.dtypes.float32,
    indices_dtype=tf.dtypes.int64,
    dense_shape_dtype=None,
    indices_shape=None
)
```

Constructs a type specification for a <a href="../tf/IndexedSlices.md"><code>tf.IndexedSlices</code></a>.

#### Args:

* <b>`shape`</b>: The dense shape of the `IndexedSlices`, or `None` to allow any
    dense shape.
* <b>`dtype`</b>: <a href="../tf/dtypes/DType.md"><code>tf.DType</code></a> of values in the `IndexedSlices`.
* <b>`indices_dtype`</b>: <a href="../tf/dtypes/DType.md"><code>tf.DType</code></a> of the `indices` in the `IndexedSlices`.  One
    of <a href="../tf/dtypes.md#int32"><code>tf.int32</code></a> or <a href="../tf/dtypes.md#int64"><code>tf.int64</code></a>.
* <b>`dense_shape_dtype`</b>: <a href="../tf/dtypes/DType.md"><code>tf.DType</code></a> of the `dense_shape` in the `IndexedSlices`.
    One of <a href="../tf/dtypes.md#int32"><code>tf.int32</code></a>, <a href="../tf/dtypes.md#int64"><code>tf.int64</code></a>, or `None` (if the `IndexedSlices` has
    no `dense_shape` tensor).
* <b>`indices_shape`</b>: The shape of the `indices` component, which indicates
    how many slices are in the `IndexedSlices`.



## Properties

<h3 id="value_type"><code>value_type</code></h3>





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



