<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.TensorSpec" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="dtype"/>
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="shape"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__ne__"/>
<meta itemprop="property" content="from_spec"/>
<meta itemprop="property" content="from_tensor"/>
<meta itemprop="property" content="is_compatible_with"/>
</div>

# tf.TensorSpec

## Class `TensorSpec`

Describes a tf.Tensor.



### Aliases:

* Class `tf.TensorSpec`
* Class `tf.compat.v1.TensorSpec`
* Class `tf.compat.v2.TensorSpec`



Defined in [`python/framework/tensor_spec.py`](/code/stable/tensorflow/python/framework/tensor_spec.py).

<!-- Placeholder for "Used in" -->

Metadata for describing the <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> objects accepted or returned
by some TensorFlow APIs.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    shape,
    dtype=tf.dtypes.float32,
    name=None
)
```

Creates a TensorSpec.


#### Args:


* <b>`shape`</b>: Value convertible to <a href="../tf/TensorShape.md"><code>tf.TensorShape</code></a>. The shape of the tensor.
* <b>`dtype`</b>: Value convertible to <a href="../tf/dtypes/DType.md"><code>tf.DType</code></a>. The type of the tensor values.
* <b>`name`</b>: Optional name for the Tensor.


#### Raises:


* <b>`TypeError`</b>: If shape is not convertible to a <a href="../tf/TensorShape.md"><code>tf.TensorShape</code></a>, or dtype is
  not convertible to a <a href="../tf/dtypes/DType.md"><code>tf.DType</code></a>.



## Properties

<h3 id="dtype"><code>dtype</code></h3>

Returns the `dtype` of elements in the tensor.


<h3 id="name"><code>name</code></h3>

Returns the (optionally provided) name of the described tensor.


<h3 id="shape"><code>shape</code></h3>

Returns the `TensorShape` that represents the shape of the tensor.




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


<h3 id="from_spec"><code>from_spec</code></h3>

``` python
@classmethod
from_spec(
    cls,
    spec,
    name=None
)
```




<h3 id="from_tensor"><code>from_tensor</code></h3>

``` python
@classmethod
from_tensor(
    cls,
    tensor,
    name=None
)
```




<h3 id="is_compatible_with"><code>is_compatible_with</code></h3>

``` python
is_compatible_with(spec_or_tensor)
```

Returns True if spec_or_tensor is compatible with this TensorSpec.

Two tensors are considered compatible if they have the same dtype
and their shapes are compatible (see <a href="../tf/TensorShape.md#is_compatible_with"><code>tf.TensorShape.is_compatible_with</code></a>).

#### Args:


* <b>`spec_or_tensor`</b>: A tf.TensorSpec or a tf.Tensor


#### Returns:

True if spec_or_tensor is compatible with self.




