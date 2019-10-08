<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.RaggedTensorSpec" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="value_type"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__ne__"/>
<meta itemprop="property" content="from_value"/>
<meta itemprop="property" content="is_compatible_with"/>
<meta itemprop="property" content="most_specific_compatible_type"/>
</div>

# tf.RaggedTensorSpec

## Class `RaggedTensorSpec`





Defined in [`tensorflow/python/ops/ragged/ragged_tensor.py`](/code/stable/tensorflow/python/ops/ragged/ragged_tensor.py).

Type specification for a <a href="../tf/RaggedTensor.md"><code>tf.RaggedTensor</code></a>.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    shape=None,
    dtype=tf.dtypes.float32,
    ragged_rank=None,
    row_splits_dtype=tf.dtypes.int64
)
```

Constructs a type specification for a <a href="../tf/RaggedTensor.md"><code>tf.RaggedTensor</code></a>.

#### Args:

* <b>`shape`</b>: The shape of the RaggedTensor, or `None` to allow any shape.  If
    a shape is specified, then all ragged dimensions must have size `None`.
* <b>`dtype`</b>: <a href="../tf/dtypes/DType.md"><code>tf.DType</code></a> of values in the RaggedTensor.
* <b>`ragged_rank`</b>: Python integer, the ragged rank of the RaggedTensor
    to be described.  Defaults to `shape.ndims - 1`.
* <b>`row_splits_dtype`</b>: `dtype` for the RaggedTensor's `row_splits` tensor.
    One of <a href="../tf/dtypes.md#int32"><code>tf.int32</code></a> or <a href="../tf/dtypes.md#int64"><code>tf.int64</code></a>.



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



