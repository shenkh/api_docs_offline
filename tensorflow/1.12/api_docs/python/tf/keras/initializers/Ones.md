<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.initializers.Ones" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.keras.initializers.Ones

## Class `Ones`

Inherits From: [`Initializer`](../../../tf/keras/initializers/Initializer.md)

### Aliases:

* Class `tf.initializers.ones`
* Class `tf.keras.initializers.Ones`
* Class `tf.keras.initializers.ones`
* Class `tf.ones_initializer`



Defined in [`tensorflow/python/ops/init_ops.py`](/code/stable/tensorflow/python/ops/init_ops.py).

Initializer that generates tensors initialized to 1.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(dtype=tf.float32)
```

Initialize self.  See help(type(self)) for accurate signature.



## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    shape,
    dtype=None,
    partition_info=None
)
```

Call self as a function.

<h3 id="from_config"><code>from_config</code></h3>

``` python
from_config(
    cls,
    config
)
```

Instantiates an initializer from a configuration dictionary.

Example:

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



