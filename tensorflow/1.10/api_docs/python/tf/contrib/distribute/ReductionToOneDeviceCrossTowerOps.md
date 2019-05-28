<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distribute.ReductionToOneDeviceCrossTowerOps" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="batch_reduce"/>
<meta itemprop="property" content="broadcast"/>
<meta itemprop="property" content="reduce"/>
</div>

# tf.contrib.distribute.ReductionToOneDeviceCrossTowerOps

## Class `ReductionToOneDeviceCrossTowerOps`

Inherits From: [`CrossTowerOps`](../../../tf/contrib/distribute/CrossTowerOps.md)



Defined in [`tensorflow/contrib/distribute/python/cross_tower_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/distribute/python/cross_tower_ops.py).

Always do reduction to one device first and then do broadcasting.

Batch reduction is done by reduction on each element one by one.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    reduce_to_device=None,
    accumulation_fn=tf.add_n
)
```

Constructor.

#### Args:

* <b>`reduce_to_device`</b>: the intermediate device to reduce to. If None, reduce
    to the first device in `destinations` of the reduce() method.
* <b>`accumulation_fn`</b>: a function that does accumulation.

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
    and destinations. If a destination is None, then the destinations
    are set to match the devices of the input PerDevice object.


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
    destinations=None
)
```

Reduce `per_device_value` to `destinations`.

It runs the reduction operation defined by `aggregation` and put the
result on `destinations`.

#### Args:

* <b>`aggregation`</b>: Indicates how a variable will be aggregated. Accepted values
    are <a href="../../../tf/VariableAggregation.md#SUM"><code>tf.VariableAggregation.SUM</code></a>, <a href="../../../tf/VariableAggregation.md#MEAN"><code>tf.VariableAggregation.MEAN</code></a>.
* <b>`per_device_value`</b>: a PerDevice object.
* <b>`destinations`</b>: the reduction destinations.


#### Returns:

a Mirrored object.


#### Raises:

* <b>`ValueError`</b>: if per_device_value is not a PerDevice object.



