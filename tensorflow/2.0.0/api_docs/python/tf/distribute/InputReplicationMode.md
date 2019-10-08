<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.distribute.InputReplicationMode" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="PER_WORKER"/>
<meta itemprop="property" content="__members__"/>
</div>

# tf.distribute.InputReplicationMode

## Class `InputReplicationMode`





Defined in [`tensorflow/python/distribute/distribute_lib.py`](/code/stable/tensorflow/python/distribute/distribute_lib.py).

Replication mode for input function.

* `PER_WORKER`: The input function will be called on each worker
  independently, creating as many input pipelines as number of workers.
  Replicas will dequeue from the local Dataset on their worker.
  <a href="../../tf/distribute/Strategy.md"><code>tf.distribute.Strategy</code></a> doesn't manage any state sharing between such
  separate input pipelines.

## Class Members

<h3 id="PER_WORKER"><code>PER_WORKER</code></h3>

<h3 id="__members__"><code>__members__</code></h3>

