<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.distribute.ReductionToOneDevice" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="batch_reduce"/>
<meta itemprop="property" content="broadcast"/>
<meta itemprop="property" content="reduce"/>
</div>

# tf.distribute.ReductionToOneDevice

## Class `ReductionToOneDevice`

Always do reduction to one device first and then do broadcasting.

Inherits From: [`CrossDeviceOps`](../../tf/distribute/CrossDeviceOps.md)

### Aliases:

* Class `tf.compat.v1.distribute.ReductionToOneDevice`
* Class `tf.compat.v2.distribute.ReductionToOneDevice`
* Class `tf.distribute.ReductionToOneDevice`



Defined in [`python/distribute/cross_device_ops.py`](/code/stable/tensorflow/python/distribute/cross_device_ops.py).

<!-- Placeholder for "Used in" -->

Batch reduction is done by reduction on each element one by one.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    reduce_to_device=None,
    accumulation_fn=None
)
```

Constructor.


#### Args:


* <b>`reduce_to_device`</b>: the intermediate device to reduce to. If None, reduce
  to the first device in `destinations` of the reduce() method.
* <b>`accumulation_fn`</b>: a function that does accumulation.  If None, then
  <a href="../../tf/math/add_n.md"><code>tf.math.add_n</code></a> is used.



## Methods

<h3 id="batch_reduce"><code>batch_reduce</code></h3>

``` python
batch_reduce(
    reduce_op,
    value_destination_pairs
)
```

Reduce PerReplica objects in a batch.

Reduce each first element in `value_destination_pairs` to each second
element which indicates the destinations.

#### Args:


* <b>`reduce_op`</b>: Indicates how per_replica_value will be reduced. Accepted
  values are <a href="../../tf/distribute/ReduceOp.md#SUM"><code>tf.distribute.ReduceOp.SUM</code></a>, <a href="../../tf/distribute/ReduceOp.md#MEAN"><code>tf.distribute.ReduceOp.MEAN</code></a>.
* <b>`value_destination_pairs`</b>: a list or a tuple of tuples of PerReplica objects
  (or tensors with device set if there is one device) and destinations.


#### Returns:

a list of Mirrored objects.



#### Raises:


* <b>`ValueError`</b>: if `value_destination_pairs` is not a list or a tuple of
  tuples of PerReplica objects and destinations

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
    reduce_op,
    per_replica_value,
    destinations
)
```

Reduce `per_replica_value` to `destinations`.

It runs the reduction operation defined by `reduce_op` and put the
result on `destinations`.

#### Args:


* <b>`reduce_op`</b>: Indicates how per_replica_value will be reduced. Accepted
  values are <a href="../../tf/distribute/ReduceOp.md#SUM"><code>tf.distribute.ReduceOp.SUM</code></a>, <a href="../../tf/distribute/ReduceOp.md#MEAN"><code>tf.distribute.ReduceOp.MEAN</code></a>.
* <b>`per_replica_value`</b>: a PerReplica object or a tensor with device set.
* <b>`destinations`</b>: the reduction destinations.


#### Returns:

a Mirrored object.



#### Raises:


* <b>`ValueError`</b>: if per_replica_value can't be converted to a PerReplica
  object.



