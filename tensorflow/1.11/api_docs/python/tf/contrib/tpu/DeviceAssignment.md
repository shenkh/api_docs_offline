<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.tpu.DeviceAssignment" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="computation_shape"/>
<meta itemprop="property" content="core_assignment"/>
<meta itemprop="property" content="num_cores_per_replica"/>
<meta itemprop="property" content="num_replicas"/>
<meta itemprop="property" content="topology"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="host_device"/>
<meta itemprop="property" content="lookup_replicas"/>
<meta itemprop="property" content="tpu_device"/>
<meta itemprop="property" content="tpu_ordinal"/>
</div>

# tf.contrib.tpu.DeviceAssignment

## Class `DeviceAssignment`





Defined in [`tensorflow/contrib/tpu/python/tpu/device_assignment.py`](https://www.tensorflow.org/code/tensorflow/contrib/tpu/python/tpu/device_assignment.py).

Mapping from logical cores in a computation to the physical TPU topology.

Prefer to use the `device_assignment()` helper to construct a
`DeviceAssignment`; it is easier if less flexible than constructing a
`DeviceAssignment` directly.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    topology,
    core_assignment
)
```

Constructs a `DeviceAssignment` object.

#### Args:

* <b>`topology`</b>: A `Topology` object that describes the physical TPU topology.
* <b>`core_assignment`</b>: A logical to physical core mapping, represented as a
    rank 3 numpy array. See the description of the `core_assignment`
    property for more details.


#### Raises:

* <b>`ValueError`</b>: If `topology` is not `Topology` object.
* <b>`ValueError`</b>: If `core_assignment` is not a rank 3 numpy array.



## Properties

<h3 id="computation_shape"><code>computation_shape</code></h3>

The computation shape.

#### Returns:

A rank-1 int32 numpy array with size equal to the TPU topology rank.
Describes the logical shape in numbers of core of each replica of the
computation in the TPU topology.


#### Returns:

The computation shape.

<h3 id="core_assignment"><code>core_assignment</code></h3>

The logical to physical core mapping.

#### Returns:

A numpy array of rank `topology_rank + 2`, with shape
`[num_replicas] + computation_shape + [topology_rank]`. Maps
(replica, logical core coordinates) pairs to physical topology
coordinates.

<h3 id="num_cores_per_replica"><code>num_cores_per_replica</code></h3>

The number of cores per replica.

<h3 id="num_replicas"><code>num_replicas</code></h3>

The number of replicas of the computation.

<h3 id="topology"><code>topology</code></h3>

A `Topology` that describes the TPU topology.



## Methods

<h3 id="host_device"><code>host_device</code></h3>

``` python
host_device(
    replica=0,
    logical_core=None,
    job=None
)
```

Returns the CPU device attached to a logical core.

<h3 id="lookup_replicas"><code>lookup_replicas</code></h3>

``` python
lookup_replicas(
    task_id,
    logical_core
)
```

Lookup replica ids by task number and logical core.

#### Args:

* <b>`task_id`</b>: TensorFlow task number.
* <b>`logical_core`</b>: A tuple of three integers which represents a logical core.

#### Returns:

A sorted list of the replicas that are attached to that task and
logical_core.

#### Raises:

* <b>`ValueError`</b>: If no replica exists in the task which contains the logical
  core.

<h3 id="tpu_device"><code>tpu_device</code></h3>

``` python
tpu_device(
    replica=0,
    logical_core=None,
    job=None
)
```

Returns the name of the TPU device assigned to a logical core.

<h3 id="tpu_ordinal"><code>tpu_ordinal</code></h3>

``` python
tpu_ordinal(
    replica=0,
    logical_core=None
)
```

Returns the ordinal of the TPU device assigned to a logical core.



