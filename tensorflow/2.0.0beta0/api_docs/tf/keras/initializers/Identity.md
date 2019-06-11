<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.initializers.Identity" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.keras.initializers.Identity

## Class `Identity`

Initializer that generates the identity matrix.

Inherits From: [`Initializer`](../../../tf/keras/initializers/Initializer.md)

### Aliases:

* Class `tf.compat.v2.initializers.Identity`
* Class `tf.compat.v2.initializers.identity`
* Class `tf.compat.v2.keras.initializers.Identity`
* Class `tf.compat.v2.keras.initializers.identity`
* Class `tf.initializers.Identity`
* Class `tf.initializers.identity`
* Class `tf.keras.initializers.Identity`
* Class `tf.keras.initializers.identity`



Defined in [`python/ops/init_ops_v2.py`](/code/stable/tensorflow/python/ops/init_ops_v2.py).

<!-- Placeholder for "Used in" -->

Only use for 2D matrices.

#### Args:


* <b>`gain`</b>: Multiplicative factor to apply to the identity matrix.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(gain=1.0)
```

Initialize self.  See help(type(self)) for accurate signature.




## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    shape,
    dtype=tf.dtypes.float32
)
```

Returns a tensor object initialized as specified by the initializer.


#### Args:


* <b>`shape`</b>: Shape of the tensor.
* <b>`dtype`</b>: Optional dtype of the tensor. Only floating point types are
 supported.


#### Raises:


* <b>`ValueError`</b>: If the dtype is not floating point

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




