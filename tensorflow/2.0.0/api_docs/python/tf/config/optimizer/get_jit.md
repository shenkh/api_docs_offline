<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.optimizer.get_jit" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.optimizer.get_jit

``` python
tf.config.optimizer.get_jit()
```



Defined in [`tensorflow/python/framework/config.py`](/code/stable/tensorflow/python/framework/config.py).

Get if JIT compilation is enabled.

Note that optimizations are only applied in graph mode, (within tf.function).

#### Returns:

If JIT compilation is enabled.