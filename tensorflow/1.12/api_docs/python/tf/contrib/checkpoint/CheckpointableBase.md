<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.checkpoint.CheckpointableBase" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.checkpoint.CheckpointableBase

## Class `CheckpointableBase`





Defined in [`tensorflow/python/training/checkpointable/base.py`](/code/stable/tensorflow/python/training/checkpointable/base.py).

Base class for `Checkpointable` objects without automatic dependencies.

This class has no __setattr__ override for performance reasons. Dependencies
must be added explicitly. Unless attribute assignment is performance-critical,
use `Checkpointable` instead. Use `CheckpointableBase` for `isinstance`
checks.

