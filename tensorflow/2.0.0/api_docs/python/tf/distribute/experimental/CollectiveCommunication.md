<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.distribute.experimental.CollectiveCommunication" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="AUTO"/>
<meta itemprop="property" content="NCCL"/>
<meta itemprop="property" content="RING"/>
<meta itemprop="property" content="__members__"/>
</div>

# tf.distribute.experimental.CollectiveCommunication

## Class `CollectiveCommunication`





Defined in [`tensorflow/python/distribute/cross_device_ops.py`](/code/stable/tensorflow/python/distribute/cross_device_ops.py).

Communication choices for CollectiveOps.

* `AUTO`: Default to runtime's automatic choices.
* `RING`: TensorFlow's ring algorithms for all-reduce and
  all-gather.
* `NCCL`: Use ncclAllReduce for all-reduce, and ring algorithms for
  all-gather.

## Class Members

<h3 id="AUTO"><code>AUTO</code></h3>

<h3 id="NCCL"><code>NCCL</code></h3>

<h3 id="RING"><code>RING</code></h3>

<h3 id="__members__"><code>__members__</code></h3>

