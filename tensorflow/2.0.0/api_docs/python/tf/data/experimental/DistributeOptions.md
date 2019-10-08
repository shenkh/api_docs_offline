<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.DistributeOptions" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="auto_shard"/>
<meta itemprop="property" content="num_devices"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__ne__"/>
<meta itemprop="property" content="__setattr__"/>
</div>

# tf.data.experimental.DistributeOptions

## Class `DistributeOptions`





Defined in [`tensorflow/python/data/experimental/ops/distribute_options.py`](/code/stable/tensorflow/python/data/experimental/ops/distribute_options.py).

Represents options for distributed data processing.

You can set the distribution options of a dataset through the
`experimental_distribute` property of <a href="../../../tf/data/Options.md"><code>tf.data.Options</code></a>; the property is
an instance of <a href="../../../tf/data/experimental/DistributeOptions.md"><code>tf.data.experimental.DistributeOptions</code></a>.

```python
options = tf.data.Options()
options.experimental_distribute.auto_shard = False
dataset = dataset.with_options(options)
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__()
```

Initialize self.  See help(type(self)) for accurate signature.



## Properties

<h3 id="auto_shard"><code>auto_shard</code></h3>

Whether the dataset should be automatically sharded when processedin a distributed fashion. This is applicable when using Keras with multi-worker/TPU distribution strategy, and by using strategy.experimental_distribute_dataset(). In other cases, this option does nothing. If None, defaults to True.

<h3 id="num_devices"><code>num_devices</code></h3>

The number of devices attached to this input pipeline. This will be automatically set by MultiDeviceIterator.



## Methods

<h3 id="__eq__"><code>__eq__</code></h3>

``` python
__eq__(other)
```

Return self==value.

<h3 id="__ne__"><code>__ne__</code></h3>

``` python
__ne__(other)
```

Return self!=value.

<h3 id="__setattr__"><code>__setattr__</code></h3>

``` python
__setattr__(
    name,
    value
)
```

Implement setattr(self, name, value).



