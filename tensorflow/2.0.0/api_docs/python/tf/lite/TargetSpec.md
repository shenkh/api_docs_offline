<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.lite.TargetSpec" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.lite.TargetSpec

## Class `TargetSpec`





Defined in [`tensorflow/lite/python/lite.py`](/code/stable/tensorflow/lite/python/lite.py).

Specification of target device.

Details about target device. Converter optimizes the generated model for
specific device.

#### Attributes:

* <b>`supported_ops`</b>: Experimental flag, subject to change. Set of OpsSet options
    supported by the device. (default set([OpsSet.TFLITE_BUILTINS]))
* <b>`supported_types`</b>: List of types for constant values on the target device.
    Supported values are types exported by lite.constants. Frequently, an
    optimization choice is driven by the most compact (i.e. smallest)
    type in this list (default [constants.FLOAT])

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    supported_ops=None,
    supported_types=None
)
```

Initialize self.  See help(type(self)) for accurate signature.



