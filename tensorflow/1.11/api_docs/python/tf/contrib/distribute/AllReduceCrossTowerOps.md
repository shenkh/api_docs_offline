<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distribute.AllReduceCrossTowerOps" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="batch_reduce"/>
<meta itemprop="property" content="broadcast"/>
<meta itemprop="property" content="reduce"/>
</div>

# tf.contrib.distribute.AllReduceCrossTowerOps

## Class `AllReduceCrossTowerOps`

Inherits From: [`CrossTowerOps`](../../../tf/contrib/distribute/CrossTowerOps.md)



Defined in [`tensorflow/contrib/distribute/python/cross_tower_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/distribute/python/cross_tower_ops.py).

Reduction using all reduce.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    all_reduce_alg='nccl',
    num_packs=1,
    agg_small_grads_max_bytes=0,
    agg_small_grads_max_group=10
)
```

All-reduce implementation of CrossTowerOps.

Before performing all-reduce, tensors will be repacked or aggregated for
more efficient cross-device transportation:
  1) If `num_packs` is non-zero, pack values into
    `num_packs` splits.
  2) Otherwise, if `agg_small_grads_max_bytes` > 0 and
    `agg_small_grads_max_group` > 0, aggregate values smaller than
    `agg_small_grads_max_bytes` into groups with at most
    `agg_small_grads_max_group` values.
  3) Otherwise, no repacking or grouping will happen.

#### Args:

* <b>`all_reduce_alg`</b>: the all-reduce algorithm to use, currently only "nccl" or
    "hierarchical_copy" are supported.
* <b>`num_packs`</b>: see above.
* <b>`agg_small_grads_max_bytes`</b>: see above.
* <b>`agg_small_grads_max_group`</b>: see above.
    tensors.



## Methods

<h3 id="batch_reduce"><code>batch_reduce</code></h3>

``` python
batch_reduce(
    aggregation,
    value_destination_pairs
)
```

Reduce PerDevice objects in a batch.

Reduce each first element in `value_destination_pairs` to each second
element which indicates the destinations.

#### Args:

* <b>`aggregation`</b>: Indicates how a variable will be aggregated. Accepted values
    are <a href="../../../tf/VariableAggregation.md#SUM"><code>tf.VariableAggregation.SUM</code></a>, <a href="../../../tf/VariableAggregation.md#MEAN"><code>tf.VariableAggregation.MEAN</code></a>.
* <b>`value_destination_pairs`</b>: a list or a tuple of tuples of PerDevice objects
    (or tensors with device set if there is one tower) and destinations.


#### Returns:

a list of Mirrored objects.


#### Raises:

* <b>`ValueError`</b>: if `value_destination_pairs` is not a list or a tuple of
    tuples of PerDevice objects and destinations

<h3 id="broadcast"><code>broadcast</code></h3>

``` python
broadcast(
    tensor,
    destinations
)
```

Broadcast the `tensor` to destinations.

#### Args:

* <b>`tensor`</b>: the tensor to broadcast.
* <b>`destinations`</b>: the broadcast destinations.


#### Returns:

a Mirrored object.

<h3 id="reduce"><code>reduce</code></h3>

``` python
reduce(
    aggregation,
    per_device_value,
    destinations
)
```

Reduce `per_device_value` to `destinations`.

It runs the reduction operation defined by `aggregation` and put the
result on `destinations`.

#### Args:

* <b>`aggregation`</b>: Indicates how a variable will be aggregated. Accepted values
    are <a href="../../../tf/VariableAggregation.md#SUM"><code>tf.VariableAggregation.SUM</code></a>, <a href="../../../tf/VariableAggregation.md#MEAN"><code>tf.VariableAggregation.MEAN</code></a>.
* <b>`per_device_value`</b>: a PerDevice object or a tensor with device set.
* <b>`destinations`</b>: the reduction destinations.


#### Returns:

a Mirrored object.


#### Raises:

* <b>`ValueError`</b>: if per_device_value is not a PerDevice object.



