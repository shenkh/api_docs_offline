<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.distribute.InputContext" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="input_pipeline_id"/>
<meta itemprop="property" content="num_input_pipelines"/>
<meta itemprop="property" content="num_replicas_in_sync"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get_per_replica_batch_size"/>
</div>

# tf.distribute.InputContext

## Class `InputContext`





Defined in [`tensorflow/python/distribute/distribute_lib.py`](/code/stable/tensorflow/python/distribute/distribute_lib.py).

A class wrapping information needed by an input function.

This is a context class that is passed to the user's input function and
contains information about the compute replicas and input pipelines. The
number of compute replicas (in sync training) helps compute the local batch
size from the desired global batch size for each replica. The input pipeline
information can be used to return a different subset of the input in each
replica (for e.g. shard the input pipeline, use a different input
source etc).

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    num_input_pipelines=1,
    input_pipeline_id=0,
    num_replicas_in_sync=1
)
```

Initializes an InputContext object.

#### Args:

* <b>`num_input_pipelines`</b>: the number of input pipelines in a cluster.
* <b>`input_pipeline_id`</b>: the current input pipeline id, should be an int in
    [0,`num_input_pipelines`).
* <b>`num_replicas_in_sync`</b>: the number of replicas that are in sync.



## Properties

<h3 id="input_pipeline_id"><code>input_pipeline_id</code></h3>

Returns the input pipeline ID.

<h3 id="num_input_pipelines"><code>num_input_pipelines</code></h3>

Returns the number of input pipelines.

<h3 id="num_replicas_in_sync"><code>num_replicas_in_sync</code></h3>

Returns the number of compute replicas in sync.



## Methods

<h3 id="get_per_replica_batch_size"><code>get_per_replica_batch_size</code></h3>

``` python
get_per_replica_batch_size(global_batch_size)
```

Returns the per-replica batch size.

#### Args:

* <b>`global_batch_size`</b>: the global batch size which should be divisible by
    `num_replicas_in_sync`.


#### Returns:

the per-replica batch size.


#### Raises:

* <b>`ValueError`</b>: if `global_batch_size` not divisible by
    `num_replicas_in_sync`.



