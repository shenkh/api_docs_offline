<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.keras.initializers.RandomUniform" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.compat.v1.keras.initializers.RandomUniform

## Class `RandomUniform`

Initializer that generates tensors with a uniform distribution.

Inherits From: [`random_uniform_initializer`](../../../../../tf/compat/v1/random_uniform_initializer.md)

### Aliases:

* Class `tf.compat.v1.keras.initializers.RandomUniform`
* Class `tf.compat.v1.keras.initializers.random_uniform`
* Class `tf.compat.v1.keras.initializers.uniform`



Defined in [`python/keras/initializers.py`](/code/stable/tensorflow/python/keras/initializers.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`minval`</b>: A python scalar or a scalar tensor. Lower bound of the range of
  random values to generate. Defaults to -0.05.
* <b>`maxval`</b>: A python scalar or a scalar tensor. Upper bound of the range of
  random values to generate. Defaults to 0.05.
* <b>`seed`</b>: A Python integer. Used to create random seeds. See
  <a href="../../../../../tf/compat/v1/set_random_seed.md"><code>tf.compat.v1.set_random_seed</code></a> for behavior.
* <b>`dtype`</b>: The data type.


#### Returns:

A RandomUniform instance.


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    minval=-0.05,
    maxval=0.05,
    seed=None,
    dtype=tf.dtypes.float32
)
```

DEPRECATED FUNCTION ARGUMENTS

Warning: SOME ARGUMENTS ARE DEPRECATED: `(dtype)`. They will be removed in a future version.
Instructions for updating:
Call initializer instance with the dtype argument instead of passing it to the constructor



## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    shape,
    dtype=None,
    partition_info=None
)
```

Returns a tensor object initialized as specified by the initializer.


#### Args:


* <b>`shape`</b>: Shape of the tensor.
* <b>`dtype`</b>: Optional dtype of the tensor. If not provided use the initializer
  dtype.
* <b>`partition_info`</b>: Optional information about the possible partitioning of a
  tensor.

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


* <b>`config`</b>: A Python dictionary. It will typically be the output of
  `get_config`.


#### Returns:

An Initializer instance.


<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```

Returns the configuration of the initializer as a JSON-serializable dict.


#### Returns:

A JSON-serializable Python dict.




