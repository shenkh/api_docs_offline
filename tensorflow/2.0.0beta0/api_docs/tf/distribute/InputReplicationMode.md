<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.distribute.InputReplicationMode" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="PER_WORKER"/>
</div>

# tf.distribute.InputReplicationMode

## Class `InputReplicationMode`

Replication mode for input function.



### Aliases:

* Class `tf.compat.v1.distribute.InputReplicationMode`
* Class `tf.compat.v2.distribute.InputReplicationMode`
* Class `tf.distribute.InputReplicationMode`



Defined in [`python/distribute/distribute_lib.py`](/code/stable/tensorflow/python/distribute/distribute_lib.py).

<!-- Placeholder for "Used in" -->

* `PER_WORKER`: The input function will be called on each worker
  independently, creating as many input pipelines as number of workers.
  Replicas will dequeue from the local Dataset on their worker.
  <a href="../../tf/distribute/Strategy.md"><code>tf.distribute.Strategy</code></a> doesn't manage any state sharing between such
  separate input pipelines.

## Class Members

* `PER_WORKER` <a id="PER_WORKER"></a>
