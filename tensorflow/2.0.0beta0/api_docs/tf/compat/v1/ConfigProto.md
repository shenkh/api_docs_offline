<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.ConfigProto" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="DeviceCountEntry"/>
<meta itemprop="property" content="Experimental"/>
<meta itemprop="property" content="allow_soft_placement"/>
<meta itemprop="property" content="cluster_def"/>
<meta itemprop="property" content="device_count"/>
<meta itemprop="property" content="device_filters"/>
<meta itemprop="property" content="experimental"/>
<meta itemprop="property" content="gpu_options"/>
<meta itemprop="property" content="graph_options"/>
<meta itemprop="property" content="inter_op_parallelism_threads"/>
<meta itemprop="property" content="intra_op_parallelism_threads"/>
<meta itemprop="property" content="isolate_session_state"/>
<meta itemprop="property" content="log_device_placement"/>
<meta itemprop="property" content="operation_timeout_in_ms"/>
<meta itemprop="property" content="placement_period"/>
<meta itemprop="property" content="rpc_options"/>
<meta itemprop="property" content="session_inter_op_thread_pool"/>
<meta itemprop="property" content="use_per_session_threads"/>
</div>

# tf.compat.v1.ConfigProto

## Class `ConfigProto`

A ProtocolMessage





Defined in [`core/protobuf/config.proto`](/code/stable/tensorflow/core/protobuf/config.proto).

<!-- Placeholder for "Used in" -->


## Child Classes
[`class DeviceCountEntry`](../../../tf/compat/v1/ConfigProto/DeviceCountEntry.md)

[`class Experimental`](../../../tf/compat/v1/ConfigProto/Experimental.md)

## Properties

<h3 id="allow_soft_placement"><code>allow_soft_placement</code></h3>

`bool allow_soft_placement`


<h3 id="cluster_def"><code>cluster_def</code></h3>

`ClusterDef cluster_def`


<h3 id="device_count"><code>device_count</code></h3>

`repeated DeviceCountEntry device_count`


<h3 id="device_filters"><code>device_filters</code></h3>

`repeated string device_filters`


<h3 id="experimental"><code>experimental</code></h3>

`Experimental experimental`


<h3 id="gpu_options"><code>gpu_options</code></h3>

`GPUOptions gpu_options`


<h3 id="graph_options"><code>graph_options</code></h3>

`GraphOptions graph_options`


<h3 id="inter_op_parallelism_threads"><code>inter_op_parallelism_threads</code></h3>

`int32 inter_op_parallelism_threads`


<h3 id="intra_op_parallelism_threads"><code>intra_op_parallelism_threads</code></h3>

`int32 intra_op_parallelism_threads`


<h3 id="isolate_session_state"><code>isolate_session_state</code></h3>

`bool isolate_session_state`


<h3 id="log_device_placement"><code>log_device_placement</code></h3>

`bool log_device_placement`


<h3 id="operation_timeout_in_ms"><code>operation_timeout_in_ms</code></h3>

`int64 operation_timeout_in_ms`


<h3 id="placement_period"><code>placement_period</code></h3>

`int32 placement_period`


<h3 id="rpc_options"><code>rpc_options</code></h3>

`RPCOptions rpc_options`


<h3 id="session_inter_op_thread_pool"><code>session_inter_op_thread_pool</code></h3>

`repeated ThreadPoolOptionProto session_inter_op_thread_pool`


<h3 id="use_per_session_threads"><code>use_per_session_threads</code></h3>

`bool use_per_session_threads`




