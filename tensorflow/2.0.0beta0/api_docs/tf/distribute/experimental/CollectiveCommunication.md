<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.distribute.experimental.CollectiveCommunication" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="AUTO"/>
<meta itemprop="property" content="NCCL"/>
<meta itemprop="property" content="RING"/>
</div>

# tf.distribute.experimental.CollectiveCommunication

## Class `CollectiveCommunication`

Communication choices for CollectiveOps.



### Aliases:

* Class `tf.compat.v1.distribute.experimental.CollectiveCommunication`
* Class `tf.compat.v2.distribute.experimental.CollectiveCommunication`
* Class `tf.distribute.experimental.CollectiveCommunication`



Defined in [`python/distribute/cross_device_ops.py`](/code/stable/tensorflow/python/distribute/cross_device_ops.py).

<!-- Placeholder for "Used in" -->

* `AUTO`: Default to runtime's automatic choices.
* `RING`: TensorFlow's ring algorithms for all-reduce and
  all-gather.
* `NCCL`: Use ncclAllReduce for all-reduce, and ring algorithms for
  all-gather.  TODO(ayushd): add ncclAllGather implementation.

## Class Members

* `AUTO` <a id="AUTO"></a>
* `NCCL` <a id="NCCL"></a>
* `RING` <a id="RING"></a>
