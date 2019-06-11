<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.experimental.get_memory_growth" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.experimental.get_memory_growth

Get if memory growth is enabled for a PhysicalDevice.

### Aliases:

* `tf.compat.v1.config.experimental.get_memory_growth`
* `tf.compat.v2.config.experimental.get_memory_growth`
* `tf.config.experimental.get_memory_growth`

``` python
tf.config.experimental.get_memory_growth(device)
```



Defined in [`python/framework/config.py`](/code/stable/tensorflow/python/framework/config.py).

<!-- Placeholder for "Used in" -->

A PhysicalDevice with memory growth set will not allocate all memory on the
device upfront.

#### For example:



```python
physical_devices = config.experimental.list_physical_devices('GPU')
assert len(physical_devices) > 0, "Not enough GPU hardware devices available"
tf.config.experimental.set_memory_growth(physical_devices[0], True)
assert tf.config.experimental.get_memory_growth(physical_devices[0]) == True
```

#### Args:


* <b>`device`</b>: PhysicalDevice to query


#### Returns:

Current memory growth setting.
