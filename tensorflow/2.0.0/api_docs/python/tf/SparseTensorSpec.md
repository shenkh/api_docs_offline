<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.SparseTensorSpec" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="dtype"/>
<meta itemprop="property" content="shape"/>
<meta itemprop="property" content="value_type"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__ne__"/>
<meta itemprop="property" content="from_value"/>
<meta itemprop="property" content="is_compatible_with"/>
<meta itemprop="property" content="most_specific_compatible_type"/>
</div>

# tf.SparseTensorSpec

## Class `SparseTensorSpec`





Defined in [`tensorflow/python/framework/sparse_tensor.py`](/code/stable/tensorflow/python/framework/sparse_tensor.py).

Type specification for a <a href="../tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a>.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    shape=None,
    dtype=tf.dtypes.float32
)
```

Constructs a type specification for a <a href="../tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a>.

#### Args:

* <b>`shape`</b>: The dense shape of the `SparseTensor`, or `None` to allow
    any dense shape.
* <b>`dtype`</b>: <a href="../tf/dtypes/DType.md"><code>tf.DType</code></a> of values in the `SparseTensor`.



## Properties

<h3 id="dtype"><code>dtype</code></h3>

The <a href="../tf/dtypes/DType.md"><code>tf.dtypes.DType</code></a> specified by this type for the SparseTensor.

<h3 id="shape"><code>shape</code></h3>

The <a href="../tf/TensorShape.md"><code>tf.TensorShape</code></a> specified by this type for the SparseTensor.

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

<h3 id="from_value"><code>from_value</code></h3>

``` python
@classmethod
from_value(
    cls,
    value
)
```



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



