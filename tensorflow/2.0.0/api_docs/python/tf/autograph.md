<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.autograph" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.autograph

Conversion of plain Python into TensorFlow graph code.

NOTE: In TensorFlow 2.0, AutoGraph is automatically applied when using
<a href="../tf/function.md"><code>tf.function</code></a>. This module contains lower-level APIs for advanced use.

For more information, see the
[AutoGraph guide](https://www.tensorflow.org/guide/autograph).

By equivalent graph code we mean code that generates a TensorFlow graph when
run. The generated graph has the same effects as the original code when executed
(for example with <a href="../tf/function.md"><code>tf.function</code></a> or `tf.compat.v1.Session.run`). In other words,
using AutoGraph can be thought of as running Python in TensorFlow.

## Modules

[`experimental`](../tf/autograph/experimental.md) module: Public API for tf.autograph.experimental namespace.

## Functions

[`set_verbosity(...)`](../tf/autograph/set_verbosity.md): Sets the AutoGraph verbosity level.

[`to_code(...)`](../tf/autograph/to_code.md): Similar to `to_graph`, but returns Python source code as a string.

[`to_graph(...)`](../tf/autograph/to_graph.md): Converts a Python entity into a TensorFlow graph.

[`trace(...)`](../tf/autograph/trace.md): Traces argument information at compilation time.

