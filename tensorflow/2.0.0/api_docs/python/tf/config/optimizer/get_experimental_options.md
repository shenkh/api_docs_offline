<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.optimizer.get_experimental_options" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.optimizer.get_experimental_options

``` python
tf.config.optimizer.get_experimental_options()
```



Defined in [`tensorflow/python/framework/config.py`](/code/stable/tensorflow/python/framework/config.py).

Get experimental optimizer options.

Refer to tf.config.optimizer.set_experimental_options for a list of current
options.

Note that optimizations are only applied in graph mode, (within tf.function).
In addition, as these are experimental options, the list is subject to change.

#### Returns:

Dictionary of configured experimental optimizer options