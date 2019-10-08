<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.optimizer.set_experimental_options" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.optimizer.set_experimental_options

``` python
tf.config.optimizer.set_experimental_options(options)
```



Defined in [`tensorflow/python/framework/config.py`](/code/stable/tensorflow/python/framework/config.py).

Set experimental optimizer options.

Note that optimizations are only applied in graph mode, (within tf.function).
In addition, as these are experimental options, the list is subject to change.

#### Args:

* <b>`options`</b>: Dictionary of experimental optimizer options to configure.
    Valid keys:
    - layout_optimizer: Optimize tensor layouts
      e.g. This will try to use NCHW layout on GPU which is faster.
    - constant_folding: Fold constants
      Statically infer the value of tensors when possible, and materialize the
      result using constants.
    - shape_optimization: Simplify computations made on shapes.
    - remapping: Remap subgraphs onto more efficient implementations.
    - arithmetic_optimization: Simplify arithmetic ops with common
      sub-expression elimination and arithmetic simplification.
    - dependency_optimization: Control dependency optimizations. Remove
      redundant control dependencies, which may enable other optimization.
      This optimizer is also essential for pruning Identity and NoOp nodes.
    - loop_optimization: Loop optimizations.
    - function_optimization: Function optimizations and inlining.
    - debug_stripper: Strips debug-related nodes from the graph.
    - disable_model_pruning: Disable removal of unnecessary ops from the graph
    - scoped_allocator_optimization: Try to allocate some independent Op
      outputs contiguously in order to merge or eliminate downstream Ops.
    - pin_to_host_optimization: Force small ops onto the CPU.
    - implementation_selector: Enable the swap of kernel implementations based
      on the device placement.
    - auto_mixed_precision: Change certain float32 ops to float16 on Volta
      GPUs and above. Without the use of loss scaling, this can cause
      numerical underflow (see
      `keras.mixed_precision.experimental.LossScaleOptimizer`).
    - disable_meta_optimizer: Disable the entire meta optimizer.
    - min_graph_nodes: The minimum number of nodes in a graph to optimizer.
      For smaller graphs, optimization is skipped.