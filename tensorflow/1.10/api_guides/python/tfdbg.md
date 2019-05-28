# TensorFlow Debugger
[TOC]

Public Python API of TensorFlow Debugger (tfdbg).

<h2 id="Functions_for_adding_debug_watches">Functions for adding debug watches</h2>

These functions help you modify `RunOptions` to specify which `Tensor`s are to
be watched when the TensorFlow graph is executed at runtime.

*   <a href="../../api_docs/python/tfdbg/add_debug_tensor_watch.md"><code>tfdbg.add_debug_tensor_watch</code></a>
*   <a href="../../api_docs/python/tfdbg/watch_graph.md"><code>tfdbg.watch_graph</code></a>
*   <a href="../../api_docs/python/tfdbg/watch_graph_with_blacklists.md"><code>tfdbg.watch_graph_with_blacklists</code></a>


<h2 id="Classes_for_debug_dump_data_and_directories">Classes for debug-dump data and directories</h2>

These classes allow you to load and inspect tensor values dumped from
TensorFlow graphs during runtime.

*   <a href="../../api_docs/python/tfdbg/DebugTensorDatum.md"><code>tfdbg.DebugTensorDatum</code></a>
*   <a href="../../api_docs/python/tfdbg/DebugDumpDir.md"><code>tfdbg.DebugDumpDir</code></a>


<h2 id="Functions_for_loading_debug_dump_data">Functions for loading debug-dump data</h2>

*   <a href="../../api_docs/python/tfdbg/load_tensor_from_event_file.md"><code>tfdbg.load_tensor_from_event_file</code></a>


<h2 id="Tensor_value_predicates">Tensor-value predicates</h2>

Built-in tensor-filter predicates to support conditional breakpoint between
runs. See `DebugDumpDir.find()` for more details.

*   <a href="../../api_docs/python/tfdbg/has_inf_or_nan.md"><code>tfdbg.has_inf_or_nan</code></a>


<h2 id="Session_wrapper_class_and_SessionRunHook_implementations">Session wrapper class and `SessionRunHook` implementations</h2>

These classes allow you to

* wrap aroundTensorFlow `Session` objects to debug plain TensorFlow models
  (see `DumpingDebugWrapperSession` and `LocalCLIDebugWrapperSession`), or
* generate `SessionRunHook` objects to debug <a href="../../api_docs/python/tf/contrib/learn.md"><code>tf.contrib.learn</code></a> models (see
  `DumpingDebugHook` and `LocalCLIDebugHook`).

*   <a href="../../api_docs/python/tfdbg/DumpingDebugHook.md"><code>tfdbg.DumpingDebugHook</code></a>
*   <a href="../../api_docs/python/tfdbg/DumpingDebugWrapperSession.md"><code>tfdbg.DumpingDebugWrapperSession</code></a>
*   <a href="../../api_docs/python/tfdbg/LocalCLIDebugHook.md"><code>tfdbg.LocalCLIDebugHook</code></a>
*   <a href="../../api_docs/python/tfdbg/LocalCLIDebugWrapperSession.md"><code>tfdbg.LocalCLIDebugWrapperSession</code></a>
