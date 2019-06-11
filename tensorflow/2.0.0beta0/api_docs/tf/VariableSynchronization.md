<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.VariableSynchronization" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="AUTO"/>
<meta itemprop="property" content="NONE"/>
<meta itemprop="property" content="ON_READ"/>
<meta itemprop="property" content="ON_WRITE"/>
</div>

# tf.VariableSynchronization

## Class `VariableSynchronization`

Indicates when a distributed variable will be synced.



### Aliases:

* Class `tf.VariableSynchronization`
* Class `tf.compat.v1.VariableSynchronization`
* Class `tf.compat.v2.VariableSynchronization`



Defined in [`python/ops/variables.py`](/code/stable/tensorflow/python/ops/variables.py).

<!-- Placeholder for "Used in" -->

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

* `AUTO` <a id="AUTO"></a>
* `NONE` <a id="NONE"></a>
* `ON_READ` <a id="ON_READ"></a>
* `ON_WRITE` <a id="ON_WRITE"></a>
