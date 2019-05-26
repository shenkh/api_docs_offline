<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.checkpoint" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.contrib.checkpoint



Defined in [`tensorflow/contrib/checkpoint/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/checkpoint/__init__.py).

Tools for working with object-based checkpoints.

Visualization and inspection:

Managing dependencies:

Checkpointable data structures:

Checkpoint management:

Saving and restoring Python state:

## Classes

[`class CheckpointManager`](../../tf/contrib/checkpoint/CheckpointManager.md): Deletes old checkpoints.

[`class Checkpointable`](../../tf/contrib/checkpoint/Checkpointable.md): Manages dependencies on other objects.

[`class CheckpointableBase`](../../tf/contrib/checkpoint/CheckpointableBase.md): Base class for `Checkpointable` objects without automatic dependencies.

[`class CheckpointableObjectGraph`](../../tf/contrib/checkpoint/CheckpointableObjectGraph.md): A ProtocolMessage

[`class List`](../../tf/contrib/checkpoint/List.md): An append-only sequence type which is checkpointable.

[`class Mapping`](../../tf/contrib/checkpoint/Mapping.md): An append-only checkpointable mapping data structure with string keys.

[`class NoDependency`](../../tf/contrib/checkpoint/NoDependency.md): Allows attribute assignment to `Checkpointable` objects with no dependency.

[`class NumpyState`](../../tf/contrib/checkpoint/NumpyState.md): A checkpointable object whose NumPy array attributes are saved/restored.

[`class UniqueNameTracker`](../../tf/contrib/checkpoint/UniqueNameTracker.md): Adds dependencies on checkpointable objects with name hints.

## Functions

[`capture_dependencies(...)`](../../tf/contrib/checkpoint/capture_dependencies.md): Capture variables created within this scope as `Template` dependencies.

[`dot_graph_from_checkpoint(...)`](../../tf/contrib/checkpoint/dot_graph_from_checkpoint.md): Visualizes an object-based checkpoint (from <a href="../../tf/train/Checkpoint.md"><code>tf.train.Checkpoint</code></a>).

[`list_objects(...)`](../../tf/contrib/checkpoint/list_objects.md): Traverse the object graph and list all accessible objects.

[`object_metadata(...)`](../../tf/contrib/checkpoint/object_metadata.md): Retrieves information about the objects in a checkpoint.

[`split_dependency(...)`](../../tf/contrib/checkpoint/split_dependency.md): Creates multiple dependencies with a synchronized save/restore.

