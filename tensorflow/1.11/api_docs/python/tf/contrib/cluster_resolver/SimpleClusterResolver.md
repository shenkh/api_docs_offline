<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.cluster_resolver.SimpleClusterResolver" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="cluster_spec"/>
<meta itemprop="property" content="master"/>
</div>

# tf.contrib.cluster_resolver.SimpleClusterResolver

## Class `SimpleClusterResolver`

Inherits From: [`ClusterResolver`](../../../tf/contrib/cluster_resolver/ClusterResolver.md)



Defined in [`tensorflow/contrib/cluster_resolver/python/training/cluster_resolver.py`](https://www.tensorflow.org/code/tensorflow/contrib/cluster_resolver/python/training/cluster_resolver.py).

Simple implementation of ClusterResolver that accepts a ClusterSpec.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    cluster_spec,
    master=''
)
```

Creates a SimpleClusterResolver from a ClusterSpec.



## Methods

<h3 id="cluster_spec"><code>cluster_spec</code></h3>

``` python
cluster_spec()
```

Returns the ClusterSpec passed into the constructor.

<h3 id="master"><code>master</code></h3>

``` python
master()
```

Returns the master address to use when creating a session.



