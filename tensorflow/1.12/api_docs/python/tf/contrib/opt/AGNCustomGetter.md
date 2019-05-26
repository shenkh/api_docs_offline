<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.opt.AGNCustomGetter" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.contrib.opt.AGNCustomGetter

## Class `AGNCustomGetter`





Defined in [`tensorflow/contrib/opt/python/training/agn_optimizer.py`](/code/stable/tensorflow/contrib/opt/python/training/agn_optimizer.py).

Custom_getter class is used to do:

1. Change trainable variables to local collection and place them at worker
  device
2. Generate global variables(global center variables)
3. Generate grad variables(gradients) which record the gradients sum
  and place them at worker device
  Notice that the class should be used with tf.replica_device_setter,
  so that the global center variables and global step variable can be placed
  at ps device.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(worker_device)
```

Args:
  worker_device: put the grad_variables on worker device



## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    getter,
    name,
    trainable,
    collections,
    *args,
    **kwargs
)
```

Call self as a function.



