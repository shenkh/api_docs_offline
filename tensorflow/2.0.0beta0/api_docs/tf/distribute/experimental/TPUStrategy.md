<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.distribute.experimental.TPUStrategy" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="extended"/>
<meta itemprop="property" content="num_replicas_in_sync"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="experimental_distribute_dataset"/>
<meta itemprop="property" content="experimental_distribute_datasets_from_function"/>
<meta itemprop="property" content="experimental_local_results"/>
<meta itemprop="property" content="experimental_make_numpy_dataset"/>
<meta itemprop="property" content="experimental_run_v2"/>
<meta itemprop="property" content="reduce"/>
<meta itemprop="property" content="scope"/>
</div>

# tf.distribute.experimental.TPUStrategy

## Class `TPUStrategy`

TPU distribution strategy implementation.

Inherits From: [`Strategy`](../../../tf/distribute/Strategy.md)

### Aliases:

* Class `tf.compat.v2.distribute.experimental.TPUStrategy`
* Class `tf.distribute.experimental.TPUStrategy`



Defined in [`python/distribute/tpu_strategy.py`](/code/stable/tensorflow/python/distribute/tpu_strategy.py).

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    tpu_cluster_resolver=None,
    steps_per_run=None,
    device_assignment=None
)
```

Initializes the TPUStrategy object.


#### Args:


* <b>`tpu_cluster_resolver`</b>: A tf.distribute.cluster_resolver.TPUClusterResolver,
    which provides information about the TPU cluster.
* <b>`steps_per_run`</b>: Number of steps to run on device before returning to the
    host. Note that this can have side-effects on performance, hooks,
    metrics, summaries etc.
    This parameter is only used when Distribution Strategy is used with
    estimator or keras.
* <b>`device_assignment`</b>: Optional `tf.contrib.tpu.DeviceAssignment` to specify
    the placement of replicas on the TPU cluster. Currently only supports
    the usecase of using a single core within a TPU cluster.



## Properties

<h3 id="extended"><code>extended</code></h3>

<a href="../../../tf/distribute/StrategyExtended.md"><code>tf.distribute.StrategyExtended</code></a> with additional methods.


<h3 id="num_replicas_in_sync"><code>num_replicas_in_sync</code></h3>

Returns number of replicas over which gradients are aggregated.




## Methods

<h3 id="experimental_distribute_dataset"><code>experimental_distribute_dataset</code></h3>

``` python
experimental_distribute_dataset(dataset)
```

Distributes a tf.data.Dataset instance provided via `dataset`.

In a multi-worker setting, we will first attempt to distribute the dataset
by attempting to detect whether the dataset is being created out of
ReaderDatasets (e.g. TFRecordDataset, TextLineDataset, etc.) and if so,
attempting to shard the input files. Note that there has to be at least one
input file per worker. If you have less than one input file per worker, we
suggest that you should disable distributing your dataset using the method
below.

If that attempt is unsuccessful (e.g. the dataset is created from a
Dataset.range), we will shard the dataset evenly at the end by appending a
`.shard` operation to the end of the processing pipeline. This will cause
the entire preprocessing pipeline for all the data to be run on every
worker, and each worker will do redundant work. We will print a warning
if this method of sharding is selected. In this case, consider using
`experimental_distribute_datasets_from_function` instead.

You can disable dataset distribution using the `auto_shard` option in
<a href="../../../tf/data/experimental/DistributeOptions.md"><code>tf.data.experimental.DistributeOptions</code></a>.

Within each host, we will also split the data among all the worker devices
(if more than one a present), and this will happen even if multi-worker
sharding is disabled using the method above.

The following is an example:

```python
strategy = tf.distribute.MirroredStrategy()

# Create a dataset
dataset = dataset_ops.Dataset.TFRecordDataset([
  "/a/1.tfr", "/a/2.tfr", "/a/3.tfr", /a/4.tfr"])

# Distribute that dataset
dist_dataset = strategy.experimental_distribute_dataset(dataset)
# Iterate over the distributed dataset
for x in dist_dataset:
  # process dataset elements
  strategy.experimental_run_v2(train_step, args=(x,))
```

#### Args:


* <b>`dataset`</b>: <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> that will be sharded across all replicas using
  the rules stated above.


#### Returns:

A "distributed `Dataset`", which acts like a <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> except
it produces "per-replica" values.


<h3 id="experimental_distribute_datasets_from_function"><code>experimental_distribute_datasets_from_function</code></h3>

``` python
experimental_distribute_datasets_from_function(dataset_fn)
```

Distributes <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> instances created by calls to `dataset_fn`.

`dataset_fn` will be called once for each worker in the strategy. Each
replica on that worker will dequeue one batch of inputs from the local
`Dataset` (i.e. if a worker has two replicas, two batches will be dequeued
from the `Dataset` every step).

This method can be used for several purposes. For example, where
`experimental_distribute_dataset` is unable to shard the input files, this
method might be used to manually shard the dataset (avoiding the slow
fallback behavior in `experimental_distribute_dataset`). In cases where the
dataset is infinite, this sharding can be done by creating dataset replicas
that differ only in their random seed.

The `dataset_fn` should take an <a href="../../../tf/distribute/InputContext.md"><code>tf.distribute.InputContext</code></a> instance where
information about batching and input replication can be accessed:

```
def dataset_fn(input_context):
  batch_size = input_context.get_per_replica_batch_size(global_batch_size)
  d = tf.data.Dataset.from_tensors([[1.]]).repeat().batch(batch_size)
  return d.shard(
      input_context.num_input_pipelines, input_context.input_pipeline_id)

inputs = strategy.experimental_distribute_datasets_from_function(dataset_fn)

for batch in inputs:
  replica_results = strategy.experimental_run_v2(replica_fn, args=(batch,))
```

IMPORTANT: The <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> returned by `dataset_fn` should have a
per-replica batch size, unlike `experimental_distribute_dataset`, which uses
the global batch size.  This may be computed using
`input_context.get_per_replica_batch_size`.

#### Args:


* <b>`dataset_fn`</b>: A function taking a <a href="../../../tf/distribute/InputContext.md"><code>tf.distribute.InputContext</code></a> instance and
  returning a <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a>.


#### Returns:

A "distributed `Dataset`", which acts like a <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> except
it produces "per-replica" values.


<h3 id="experimental_local_results"><code>experimental_local_results</code></h3>

``` python
experimental_local_results(value)
```

Returns the list of all local per-replica values contained in `value`.

Note: This only returns values on the workers initiated by this client.
When using a <a href="../../../tf/distribute/Strategy.md"><code>tf.distribute.Strategy</code></a> like
<a href="../../../tf/distribute/experimental/MultiWorkerMirroredStrategy.md"><code>tf.distribute.experimental.MultiWorkerMirroredStrategy</code></a>, each worker
will be its own client, and this function will only return values
computed on that worker.

#### Args:


* <b>`value`</b>: A value returned by `experimental_run()`, `experimental_run_v2()`,
  `extended.call_for_each_replica()`, or a variable created in `scope`.


#### Returns:

A tuple of values contained in `value`. If `value` represents a single
value, this returns `(value,).`


<h3 id="experimental_make_numpy_dataset"><code>experimental_make_numpy_dataset</code></h3>

``` python
experimental_make_numpy_dataset(numpy_input)
```

Makes a dataset for input provided via a numpy array.

This avoids adding `numpy_input` as a large constant in the graph,
and copies the data to the machine or machines that will be processing
the input.

#### Args:


* <b>`numpy_input`</b>: A nest of NumPy input arrays that will be distributed evenly
  across all replicas. Note that lists of Numpy arrays are stacked,
  as that is normal <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> behavior.


#### Returns:

A <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> representing `numpy_input`.


<h3 id="experimental_run_v2"><code>experimental_run_v2</code></h3>

``` python
experimental_run_v2(
    fn,
    args=(),
    kwargs=None
)
```

See base class.


<h3 id="reduce"><code>reduce</code></h3>

``` python
reduce(
    reduce_op,
    value,
    axis
)
```

Reduce `value` across replicas.

Given a per-replica value returned by `experimental_run_v2`, say a
per-example loss, the batch will be divided across all the replicas.  This
function allows you to aggregate across replicas and optionally also across
batch elements.  For example, if you have a global batch size of 8 and 2
replicas, values for examples `[0, 1, 2, 3]` will be on replica 0 and
`[4, 5, 6, 7]` will be on replica 1. By default, `reduce` will just
aggregate across replicas, returning `[0+4, 1+5, 2+6, 3+7]`. This is useful
when each replica is computing a scalar or some other value that doesn't
have a "batch" dimension (like a gradient). More often you will want to
aggregate across the global batch, which you can get by specifying the batch
dimension as the `axis`, typically `axis=0`. In this case it would return a
scalar `0+1+2+3+4+5+6+7`.

If there is a last partial batch, you will need to specify an axis so
that the resulting shape is consistent across replicas. So if the last
batch has size 6 and it is divided into [0, 1, 2, 3] and [4, 5], you
would get a shape mismatch unless you specify `axis=0`. If you specify
<a href="../../../tf/distribute/ReduceOp.md#MEAN"><code>tf.distribute.ReduceOp.MEAN</code></a>, using `axis=0` will use the correct
denominator of 6. Contrast this with computing `reduce_mean` to get a
scalar value on each replica and this function to average those means,
which will weigh some values `1/8` and others `1/4`.

#### Args:


* <b>`reduce_op`</b>: A <a href="../../../tf/distribute/ReduceOp.md"><code>tf.distribute.ReduceOp</code></a> value specifying how values should
  be combined.
* <b>`value`</b>: A "per replica" value, e.g. returned by `experimental_run_v2` to
  be combined into a single tensor.
* <b>`axis`</b>: Specifies the dimension to reduce along within each
  replica's tensor. Should typically be set to the batch dimension, or
  `None` to only reduce across replicas (e.g. if the tensor has no batch
  dimension).


#### Returns:

A `Tensor`.


<h3 id="scope"><code>scope</code></h3>

``` python
scope()
```

Returns a context manager selecting this Strategy as current.

Inside a `with strategy.scope():` code block, this thread
will use a variable creator set by `strategy`, and will
enter its "cross-replica context".

#### Returns:

A context manager.




