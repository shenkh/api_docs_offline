<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tfdbg" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tfdbg



Defined in [`tensorflow/python/debug/__init__.py`](/code/stable/tensorflow/python/debug/__init__.py).

Public Python API of TensorFlow Debugger (tfdbg).

See the [TFDBG](https://www.tensorflow.org/guide/debugger) guide.




## Classes

[`class DebugDumpDir`](./tfdbg/DebugDumpDir.md): Data set from a debug-dump directory on filesystem.

[`class DebugTensorDatum`](./tfdbg/DebugTensorDatum.md): A single tensor dumped by TensorFlow Debugger (tfdbg).

[`class DumpingDebugHook`](./tfdbg/DumpingDebugHook.md): A debugger hook that dumps debug data to filesystem.

[`class DumpingDebugWrapperSession`](./tfdbg/DumpingDebugWrapperSession.md): Debug Session wrapper that dumps debug data to filesystem.

[`class GradientsDebugger`](./tfdbg/GradientsDebugger.md): Gradients Debugger.

[`class GrpcDebugHook`](./tfdbg/GrpcDebugHook.md): A hook that streams debugger-related events to any grpc_debug_server.

[`class GrpcDebugWrapperSession`](./tfdbg/GrpcDebugWrapperSession.md): Debug Session wrapper that send debug data to gRPC stream(s).

[`class LocalCLIDebugHook`](./tfdbg/LocalCLIDebugHook.md): Command-line-interface debugger hook.

[`class LocalCLIDebugWrapperSession`](./tfdbg/LocalCLIDebugWrapperSession.md): Concrete subclass of BaseDebugWrapperSession implementing a local CLI.

[`class TensorBoardDebugHook`](./tfdbg/TensorBoardDebugHook.md): A tfdbg hook that can be used with TensorBoard Debugger Plugin.

[`class TensorBoardDebugWrapperSession`](./tfdbg/TensorBoardDebugWrapperSession.md): A tfdbg Session wrapper that can be used with TensorBoard Debugger Plugin.

[`class WatchOptions`](./tfdbg/WatchOptions.md): Type for return values of watch_fn.

## Functions

[`add_debug_tensor_watch(...)`](./tfdbg/add_debug_tensor_watch.md): Add watch on a `Tensor` to `RunOptions`.

[`has_inf_or_nan(...)`](./tfdbg/has_inf_or_nan.md): A predicate for whether a tensor consists of any bad numerical values.

[`load_tensor_from_event(...)`](./tfdbg/load_tensor_from_event.md): Load a tensor from an Event proto.

[`load_tensor_from_event_file(...)`](./tfdbg/load_tensor_from_event_file.md): Load a tensor from an event file.

[`reconstruct_non_debug_graph_def(...)`](./tfdbg/reconstruct_non_debug_graph_def.md): Reconstruct original (non-debugger-decorated) partition GraphDef.

[`watch_graph(...)`](./tfdbg/watch_graph.md): Add debug watches to `RunOptions` for a TensorFlow graph.

[`watch_graph_with_blacklists(...)`](./tfdbg/watch_graph_with_blacklists.md): Add debug tensor watches, blacklisting nodes and op types.

