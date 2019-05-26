<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distribute.DistributeConfig" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="eval_distribute"/>
<meta itemprop="property" content="remote_cluster"/>
<meta itemprop="property" content="train_distribute"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.contrib.distribute.DistributeConfig

## Class `DistributeConfig`





Defined in [`tensorflow/python/distribute/distribute_config.py`](https://www.tensorflow.org/code/tensorflow/python/distribute/distribute_config.py).

A config tuple for distribution strategies.

#### Attributes:

* <b>`train_distribute`</b>: a `DistributionStrategy` object for training.
* <b>`eval_distribute`</b>: an optional `DistributionStrategy` object for
    evaluation.
* <b>`remote_cluster`</b>: a dict, `ClusterDef` or `ClusterSpec` object specifying
    the cluster configurations. If this is given, the `train_and_evaluate`
    method will be running as a standalone client which connects to the
    cluster for training.

<h2 id="__new__"><code>__new__</code></h2>

``` python
@staticmethod
__new__(
    cls,
    train_distribute=None,
    eval_distribute=None,
    remote_cluster=None
)
```

Create new instance of DistributeConfig(train_distribute, eval_distribute, remote_cluster)



## Properties

<h3 id="eval_distribute"><code>eval_distribute</code></h3>

Alias for field number 1

<h3 id="remote_cluster"><code>remote_cluster</code></h3>

Alias for field number 2

<h3 id="train_distribute"><code>train_distribute</code></h3>

Alias for field number 0



