<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.set_soft_device_placement" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.set_soft_device_placement

Set if soft device placement is enabled.

### Aliases:

* `tf.compat.v1.config.set_soft_device_placement`
* `tf.compat.v2.config.set_soft_device_placement`
* `tf.config.set_soft_device_placement`

``` python
tf.config.set_soft_device_placement(enabled)
```



Defined in [`python/framework/config.py`](/code/stable/tensorflow/python/framework/config.py).

<!-- Placeholder for "Used in" -->

If enabled, an op will be placed on CPU if any of the following are true
  1. there's no GPU implementation for the OP
  2. no GPU devices are known or registered
  3. need to co-locate with reftype input(s) which are from CPU

#### Args:


* <b>`enabled`</b>: Whether to enable soft placement.