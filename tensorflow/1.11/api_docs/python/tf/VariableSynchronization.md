<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.VariableSynchronization" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="AUTO"/>
<meta itemprop="property" content="NONE"/>
<meta itemprop="property" content="ON_READ"/>
<meta itemprop="property" content="ON_WRITE"/>
<meta itemprop="property" content="__members__"/>
</div>

# tf.VariableSynchronization

## Class `VariableSynchronization`





Defined in [`tensorflow/python/ops/variables.py`](https://www.tensorflow.org/code/tensorflow/python/ops/variables.py).

Indicates when a distributed variable will be synced.

* `AUTO`: Indicates that the synchronization will be determined by the current
  `DistributionStrategy` (eg. With `MirroredStrategy` this would be
  `ON_WRITE`).
* `NONE`: Indicates that there will only be one copy of the variable, so
  there is no need to sync.
* `ON_WRITE`: Indicates that the variable will be updated across devices
  every time it is written.
* `ON_READ`: Indicates that the variable will be aggregated across devices
  when it is read (eg. when checkpointing or when evaluating an op that uses
  the variable).

## Class Members

<h3 id="AUTO"><code>AUTO</code></h3>

<h3 id="NONE"><code>NONE</code></h3>

<h3 id="ON_READ"><code>ON_READ</code></h3>

<h3 id="ON_WRITE"><code>ON_WRITE</code></h3>

<h3 id="__members__"><code>__members__</code></h3>

