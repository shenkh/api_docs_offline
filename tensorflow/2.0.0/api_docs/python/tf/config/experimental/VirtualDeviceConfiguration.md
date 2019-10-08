<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.experimental.VirtualDeviceConfiguration" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="memory_limit"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.config.experimental.VirtualDeviceConfiguration

## Class `VirtualDeviceConfiguration`





Defined in [`tensorflow/python/eager/context.py`](/code/stable/tensorflow/python/eager/context.py).

Configuration class for virtual devices for a PhysicalDevice.

#### Fields:

* <b>`memory_limit`</b>: (optional) Maximum memory (in MB) to allocate on the virtual
    device. Currently only supported for GPUs.

<h2 id="__new__"><code>__new__</code></h2>

``` python
@staticmethod
__new__(
    cls,
    memory_limit=None
)
```

Create new instance of VirtualDeviceConfiguration(memory_limit,)



## Properties

<h3 id="memory_limit"><code>memory_limit</code></h3>





