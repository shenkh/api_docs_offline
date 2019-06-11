<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.profiler.GraphNodeProto" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="InputShapesEntry"/>
<meta itemprop="property" content="accelerator_exec_micros"/>
<meta itemprop="property" content="children"/>
<meta itemprop="property" content="cpu_exec_micros"/>
<meta itemprop="property" content="devices"/>
<meta itemprop="property" content="exec_micros"/>
<meta itemprop="property" content="float_ops"/>
<meta itemprop="property" content="input_shapes"/>
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="output_bytes"/>
<meta itemprop="property" content="parameters"/>
<meta itemprop="property" content="peak_bytes"/>
<meta itemprop="property" content="requested_bytes"/>
<meta itemprop="property" content="residual_bytes"/>
<meta itemprop="property" content="run_count"/>
<meta itemprop="property" content="shapes"/>
<meta itemprop="property" content="tensor_value"/>
<meta itemprop="property" content="total_accelerator_exec_micros"/>
<meta itemprop="property" content="total_cpu_exec_micros"/>
<meta itemprop="property" content="total_definition_count"/>
<meta itemprop="property" content="total_exec_micros"/>
<meta itemprop="property" content="total_float_ops"/>
<meta itemprop="property" content="total_output_bytes"/>
<meta itemprop="property" content="total_parameters"/>
<meta itemprop="property" content="total_peak_bytes"/>
<meta itemprop="property" content="total_requested_bytes"/>
<meta itemprop="property" content="total_residual_bytes"/>
<meta itemprop="property" content="total_run_count"/>
</div>

# tf.compat.v1.profiler.GraphNodeProto

## Class `GraphNodeProto`

A ProtocolMessage





Defined in [`core/profiler/tfprof_output.proto`](/code/stable/tensorflow/core/profiler/tfprof_output.proto).

<!-- Placeholder for "Used in" -->


## Child Classes
[`class InputShapesEntry`](../../../../tf/compat/v1/profiler/GraphNodeProto/InputShapesEntry.md)

## Properties

<h3 id="accelerator_exec_micros"><code>accelerator_exec_micros</code></h3>

`int64 accelerator_exec_micros`


<h3 id="children"><code>children</code></h3>

`repeated GraphNodeProto children`


<h3 id="cpu_exec_micros"><code>cpu_exec_micros</code></h3>

`int64 cpu_exec_micros`


<h3 id="devices"><code>devices</code></h3>

`repeated string devices`


<h3 id="exec_micros"><code>exec_micros</code></h3>

`int64 exec_micros`


<h3 id="float_ops"><code>float_ops</code></h3>

`int64 float_ops`


<h3 id="input_shapes"><code>input_shapes</code></h3>

`repeated InputShapesEntry input_shapes`


<h3 id="name"><code>name</code></h3>

`string name`


<h3 id="output_bytes"><code>output_bytes</code></h3>

`int64 output_bytes`


<h3 id="parameters"><code>parameters</code></h3>

`int64 parameters`


<h3 id="peak_bytes"><code>peak_bytes</code></h3>

`int64 peak_bytes`


<h3 id="requested_bytes"><code>requested_bytes</code></h3>

`int64 requested_bytes`


<h3 id="residual_bytes"><code>residual_bytes</code></h3>

`int64 residual_bytes`


<h3 id="run_count"><code>run_count</code></h3>

`int64 run_count`


<h3 id="shapes"><code>shapes</code></h3>

`repeated TensorShapeProto shapes`


<h3 id="tensor_value"><code>tensor_value</code></h3>

`TFProfTensorProto tensor_value`


<h3 id="total_accelerator_exec_micros"><code>total_accelerator_exec_micros</code></h3>

`int64 total_accelerator_exec_micros`


<h3 id="total_cpu_exec_micros"><code>total_cpu_exec_micros</code></h3>

`int64 total_cpu_exec_micros`


<h3 id="total_definition_count"><code>total_definition_count</code></h3>

`int64 total_definition_count`


<h3 id="total_exec_micros"><code>total_exec_micros</code></h3>

`int64 total_exec_micros`


<h3 id="total_float_ops"><code>total_float_ops</code></h3>

`int64 total_float_ops`


<h3 id="total_output_bytes"><code>total_output_bytes</code></h3>

`int64 total_output_bytes`


<h3 id="total_parameters"><code>total_parameters</code></h3>

`int64 total_parameters`


<h3 id="total_peak_bytes"><code>total_peak_bytes</code></h3>

`int64 total_peak_bytes`


<h3 id="total_requested_bytes"><code>total_requested_bytes</code></h3>

`int64 total_requested_bytes`


<h3 id="total_residual_bytes"><code>total_residual_bytes</code></h3>

`int64 total_residual_bytes`


<h3 id="total_run_count"><code>total_run_count</code></h3>

`int64 total_run_count`




