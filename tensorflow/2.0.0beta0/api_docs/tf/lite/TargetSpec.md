<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.lite.TargetSpec" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.lite.TargetSpec

## Class `TargetSpec`

Specification of target device.



### Aliases:

* Class `tf.compat.v1.lite.TargetSpec`
* Class `tf.compat.v2.lite.TargetSpec`
* Class `tf.lite.TargetSpec`



Defined in [`lite/python/lite.py`](/code/stable/tensorflow/lite/python/lite.py).

<!-- Placeholder for "Used in" -->

Details about target device. Converter optimizes the generated model for
specific device.

#### Attributes:


* <b>`supported_ops`</b>: Experimental flag, subject to change. Set of OpsSet options
  supported by the device. (default set([OpsSet.TFLITE_BUILTINS]))

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(supported_ops=None)
```

Initialize self.  See help(type(self)) for accurate signature.




