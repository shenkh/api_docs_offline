<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.constant_initializer" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.constant_initializer

## Class `constant_initializer`

Initializer that generates tensors with constant values.

Inherits From: [`Initializer`](../tf/keras/initializers/Initializer.md)

### Aliases:

* Class `tf.compat.v2.constant_initializer`
* Class `tf.compat.v2.initializers.Constant`
* Class `tf.compat.v2.initializers.constant`
* Class `tf.compat.v2.keras.initializers.Constant`
* Class `tf.compat.v2.keras.initializers.constant`
* Class `tf.constant_initializer`
* Class `tf.initializers.Constant`
* Class `tf.initializers.constant`
* Class `tf.keras.initializers.Constant`
* Class `tf.keras.initializers.constant`



Defined in [`python/ops/init_ops_v2.py`](/code/stable/tensorflow/python/ops/init_ops_v2.py).

<!-- Placeholder for "Used in" -->

The resulting tensor is populated with values of type `dtype`, as
specified by arguments `value` following the desired `shape` of the
new tensor (see examples below).

The argument `value` can be a constant value, or a list of values of type
`dtype`. If `value` is a list, then the length of the list must be less
than or equal to the number of elements implied by the desired shape of the
tensor. In the case where the total number of elements in `value` is less
than the number of elements required by the tensor shape, the last element
in `value` will be used to fill the remaining entries. If the total number of
elements in `value` is greater than the number of elements required by the
tensor shape, the initializer will raise a `ValueError`.

#### Args:


* <b>`value`</b>: A Python scalar, list or tuple of values, or a N-dimensional numpy
  array. All elements of the initialized variable will be set to the
  corresponding value in the `value` argument.


#### Raises:


* <b>`TypeError`</b>: If the input `value` is not one of the expected types.


#### Examples:

The following example can be rewritten using a numpy.ndarray instead
of the `value` list, even reshaped, as shown in the two commented lines
below the `value` list initialization.


```python
  >>> import numpy as np
  >>> import tensorflow as tf

  >>> value = [0, 1, 2, 3, 4, 5, 6, 7]
  >>> # value = np.array(value)
  >>> # value = value.reshape([2, 4])
  >>> init = tf.compat.v1.constant_initializer(value)

  >>> print('fitting shape:')
  >>> with tf.compat.v1.Session():
  >>>   x = tf.compat.v1.get_variable('x', shape=[2, 4], initializer=init)
  >>>   x.initializer.run()
  >>>   print(x.eval())

  fitting shape:
  [[ 0.  1.  2.  3.]
   [ 4.  5.  6.  7.]]

  >>> print('larger shape:')
  >>> with tf.compat.v1.Session():
  >>>   x = tf.compat.v1.get_variable('x', shape=[3, 4], initializer=init)
  >>>   x.initializer.run()
  >>>   print(x.eval())

  larger shape:
  [[ 0.  1.  2.  3.]
   [ 4.  5.  6.  7.]
   [ 7.  7.  7.  7.]]

  >>> print('smaller shape:')
  >>> with tf.compat.v1.Session():
  >>>   x = tf.compat.v1.get_variable('x', shape=[2, 3], initializer=init)

  ValueError: Too many elements provided. Needed at most 6, but received 8
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(value=0)
```

Initialize self.  See help(type(self)) for accurate signature.




## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    shape,
    dtype=None
)
```

Returns a tensor object initialized as specified by the initializer.


#### Args:


* <b>`shape`</b>: Shape of the tensor.
* <b>`dtype`</b>: Optional dtype of the tensor. If not provided the dtype of the
 tensor created will be the type of the inital value.


#### Raises:


* <b>`TypeError`</b>: If the initializer cannot create a tensor of the requested
 dtype.

<h3 id="from_config"><code>from_config</code></h3>

``` python
from_config(
    cls,
    config
)
```

Instantiates an initializer from a configuration dictionary.


#### Example:



```python
initializer = RandomUniform(-1, 1)
config = initializer.get_config()
initializer = RandomUniform.from_config(config)
```

#### Args:


* <b>`config`</b>: A Python dictionary.
  It will typically be the output of `get_config`.


#### Returns:

An Initializer instance.


<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```

Returns the configuration of the initializer as a JSON-serializable dict.


#### Returns:

A JSON-serializable Python dict.




