<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.queue_runner" />
</div>

# Module: tf.train.queue_runner



Defined in [`tensorflow/train/queue_runner/__init__.py`](https://www.tensorflow.org/code/tensorflow/train/queue_runner/__init__.py).

Create threads to run multiple enqueue ops.

## Classes

[`class QueueRunner`](../../tf/train/QueueRunner.md): Holds a list of enqueue operations for a queue, each to be run in a thread.

## Functions

[`add_queue_runner(...)`](../../tf/train/add_queue_runner.md): Adds a `QueueRunner` to a collection in the graph.

[`start_queue_runners(...)`](../../tf/train/start_queue_runners.md): Starts all queue runners collected in the graph.

