<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.enable_v2_tensorshape" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.enable_v2_tensorshape

In TensorFlow 2.0, iterating over a TensorShape instance returns values.

``` python
tf.compat.v1.enable_v2_tensorshape()
```



Defined in [`python/framework/tensor_shape.py`](/code/stable/tensorflow/python/framework/tensor_shape.py).

<!-- Placeholder for "Used in" -->

This enables the new behavior.

Concretely, `tensor_shape[i]` returned a Dimension instance in V1, but
it V2 it returns either an integer, or None.

#### Examples:



```
#######################
# If you had this in V1:
value = tensor_shape[i].value

# Do this in V2 instead:
value = tensor_shape[i]

#######################
# If you had this in V1:
for dim in tensor_shape:
  value = dim.value
  print(value)

# Do this in V2 instead:
for value in tensor_shape:
  print(value)

#######################
# If you had this in V1:
dim = tensor_shape[i]
dim.assert_is_compatible_with(other_shape)  # or using any other shape method

# Do this in V2 instead:
if tensor_shape.rank is None:
  dim = Dimension(None)
else:
  dim = tensor_shape.dims[i]
dim.assert_is_compatible_with(other_shape)  # or using any other shape method

# The V2 suggestion above is more explicit, which will save you from
# the following trap (present in V1):
# you might do in-place modifications to `dim` and expect them to be reflected
# in `tensor_shape[i]`, but they would not be.
```