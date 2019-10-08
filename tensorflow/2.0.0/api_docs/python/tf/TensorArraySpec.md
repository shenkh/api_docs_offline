<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.TensorArraySpec" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="value_type"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__ne__"/>
<meta itemprop="property" content="from_value"/>
<meta itemprop="property" content="is_compatible_with"/>
<meta itemprop="property" content="most_specific_compatible_type"/>
</div>

# tf.TensorArraySpec

## Class `TensorArraySpec`

Inherits From: [`TypeSpec`](../tf/TypeSpec.md)



Defined in [`tensorflow/python/ops/tensor_array_ops.py`](/code/stable/tensorflow/python/ops/tensor_array_ops.py).

Type specification for a <a href="../tf/TensorArray.md"><code>tf.TensorArray</code></a>.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    element_shape=None,
    dtype=tf.dtypes.float32,
    dynamic_size=False,
    infer_shape=True
)
```

Constructs a type specification for a <a href="../tf/TensorArray.md"><code>tf.TensorArray</code></a>.

#### Args:

* <b>`element_shape`</b>: The shape of each element in the `TensorArray`.
* <b>`dtype`</b>: Data type of the `TensorArray`.
* <b>`dynamic_size`</b>: Whether the `TensorArray` can grow past its initial size.
* <b>`infer_shape`</b>: Whether shape inference is enabled.



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

<h3 id="from_value"><code>from_value</code></h3>

``` python
@staticmethod
from_value(value)
```



<h3 id="is_compatible_with"><code>is_compatible_with</code></h3>

``` python
is_compatible_with(other)
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



