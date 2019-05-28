# Inputs and Readers

Note: Functions taking `Tensor` arguments can also take anything accepted by
<a href="../../api_docs/python/tf/convert_to_tensor.md"><code>tf.convert_to_tensor</code></a>.

[TOC]

<h2 id="Placeholders">Placeholders</h2>

TensorFlow provides a placeholder operation that must be fed with data
on execution.  For more info, see the section on <a href="../../api_guides/python/reading_data.md#Feeding">Feeding data</a>.

*   <a href="../../api_docs/python/tf/placeholder.md"><code>tf.placeholder</code></a>
*   <a href="../../api_docs/python/tf/placeholder_with_default.md"><code>tf.placeholder_with_default</code></a>

For feeding `SparseTensor`s which are composite type,
there is a convenience function:

*   <a href="../../api_docs/python/tf/sparse_placeholder.md"><code>tf.sparse_placeholder</code></a>

<h2 id="Readers">Readers</h2>

TensorFlow provides a set of Reader classes for reading data formats.
For more information on inputs and readers, see <a href="../../api_guides/python/reading_data.md">Reading data</a>.

*   <a href="../../api_docs/python/tf/ReaderBase.md"><code>tf.ReaderBase</code></a>
*   <a href="../../api_docs/python/tf/TextLineReader.md"><code>tf.TextLineReader</code></a>
*   <a href="../../api_docs/python/tf/WholeFileReader.md"><code>tf.WholeFileReader</code></a>
*   <a href="../../api_docs/python/tf/IdentityReader.md"><code>tf.IdentityReader</code></a>
*   <a href="../../api_docs/python/tf/TFRecordReader.md"><code>tf.TFRecordReader</code></a>
*   <a href="../../api_docs/python/tf/FixedLengthRecordReader.md"><code>tf.FixedLengthRecordReader</code></a>

<h2 id="Converting">Converting</h2>

TensorFlow provides several operations that you can use to convert various data
formats into tensors.

*   <a href="../../api_docs/python/tf/decode_csv.md"><code>tf.decode_csv</code></a>
*   <a href="../../api_docs/python/tf/decode_raw.md"><code>tf.decode_raw</code></a>

- - -

### Example protocol buffer

TensorFlow's <a href="../../api_guides/python/reading_data.md#standard_tensorflow_format">recommended format for training examples</a>
is serialized `Example` protocol buffers, [described
here](https://www.tensorflow.org/code/tensorflow/core/example/example.proto).
They contain `Features`, [described
here](https://www.tensorflow.org/code/tensorflow/core/example/feature.proto).

*   <a href="../../api_docs/python/tf/VarLenFeature.md"><code>tf.VarLenFeature</code></a>
*   <a href="../../api_docs/python/tf/FixedLenFeature.md"><code>tf.FixedLenFeature</code></a>
*   <a href="../../api_docs/python/tf/FixedLenSequenceFeature.md"><code>tf.FixedLenSequenceFeature</code></a>
*   <a href="../../api_docs/python/tf/SparseFeature.md"><code>tf.SparseFeature</code></a>
*   <a href="../../api_docs/python/tf/parse_example.md"><code>tf.parse_example</code></a>
*   <a href="../../api_docs/python/tf/parse_single_example.md"><code>tf.parse_single_example</code></a>
*   <a href="../../api_docs/python/tf/parse_tensor.md"><code>tf.parse_tensor</code></a>
*   <a href="../../api_docs/python/tf/decode_json_example.md"><code>tf.decode_json_example</code></a>

<h2 id="Queues">Queues</h2>

TensorFlow provides several implementations of 'Queues', which are
structures within the TensorFlow computation graph to stage pipelines
of tensors together. The following describe the basic Queue interface
and some implementations.  To see an example use, see <a href="../../api_guides/python/threading_and_queues.md">Threading and Queues</a>.

*   <a href="../../api_docs/python/tf/QueueBase.md"><code>tf.QueueBase</code></a>
*   <a href="../../api_docs/python/tf/FIFOQueue.md"><code>tf.FIFOQueue</code></a>
*   <a href="../../api_docs/python/tf/PaddingFIFOQueue.md"><code>tf.PaddingFIFOQueue</code></a>
*   <a href="../../api_docs/python/tf/RandomShuffleQueue.md"><code>tf.RandomShuffleQueue</code></a>
*   <a href="../../api_docs/python/tf/PriorityQueue.md"><code>tf.PriorityQueue</code></a>

<h2 id="Conditional_Accumulators">Conditional Accumulators</h2>

*   <a href="../../api_docs/python/tf/ConditionalAccumulatorBase.md"><code>tf.ConditionalAccumulatorBase</code></a>
*   <a href="../../api_docs/python/tf/ConditionalAccumulator.md"><code>tf.ConditionalAccumulator</code></a>
*   <a href="../../api_docs/python/tf/SparseConditionalAccumulator.md"><code>tf.SparseConditionalAccumulator</code></a>

<h2 id="Dealing_with_the_filesystem">Dealing with the filesystem</h2>

*   <a href="../../api_docs/python/tf/matching_files.md"><code>tf.matching_files</code></a>
*   <a href="../../api_docs/python/tf/read_file.md"><code>tf.read_file</code></a>
*   <a href="../../api_docs/python/tf/write_file.md"><code>tf.write_file</code></a>

<h2 id="Input_pipeline">Input pipeline</h2>

TensorFlow functions for setting up an input-prefetching pipeline.
Please see the <a href="../../api_guides/python/reading_data.md">reading data how-to</a>
for context.

### Beginning of an input pipeline

The "producer" functions add a queue to the graph and a corresponding
`QueueRunner` for running the subgraph that fills that queue.

*   <a href="../../api_docs/python/tf/train/match_filenames_once.md"><code>tf.train.match_filenames_once</code></a>
*   <a href="../../api_docs/python/tf/train/limit_epochs.md"><code>tf.train.limit_epochs</code></a>
*   <a href="../../api_docs/python/tf/train/input_producer.md"><code>tf.train.input_producer</code></a>
*   <a href="../../api_docs/python/tf/train/range_input_producer.md"><code>tf.train.range_input_producer</code></a>
*   <a href="../../api_docs/python/tf/train/slice_input_producer.md"><code>tf.train.slice_input_producer</code></a>
*   <a href="../../api_docs/python/tf/train/string_input_producer.md"><code>tf.train.string_input_producer</code></a>

### Batching at the end of an input pipeline

These functions add a queue to the graph to assemble a batch of
examples, with possible shuffling.  They also add a `QueueRunner` for
running the subgraph that fills that queue.

Use <a href="../../api_docs/python/tf/train/batch.md"><code>tf.train.batch</code></a> or <a href="../../api_docs/python/tf/train/batch_join.md"><code>tf.train.batch_join</code></a> for batching
examples that have already been well shuffled.  Use
<a href="../../api_docs/python/tf/train/shuffle_batch.md"><code>tf.train.shuffle_batch</code></a> or
<a href="../../api_docs/python/tf/train/shuffle_batch_join.md"><code>tf.train.shuffle_batch_join</code></a> for examples that would
benefit from additional shuffling.

Use <a href="../../api_docs/python/tf/train/batch.md"><code>tf.train.batch</code></a> or <a href="../../api_docs/python/tf/train/shuffle_batch.md"><code>tf.train.shuffle_batch</code></a> if you want a
single thread producing examples to batch, or if you have a
single subgraph producing examples but you want to run it in *N* threads
(where you increase *N* until it can keep the queue full).  Use
<a href="../../api_docs/python/tf/train/batch_join.md"><code>tf.train.batch_join</code></a> or <a href="../../api_docs/python/tf/train/shuffle_batch_join.md"><code>tf.train.shuffle_batch_join</code></a>
if you have *N* different subgraphs producing examples to batch and you
want them run by *N* threads. Use `maybe_*` to enqueue conditionally.

*   <a href="../../api_docs/python/tf/train/batch.md"><code>tf.train.batch</code></a>
*   <a href="../../api_docs/python/tf/train/maybe_batch.md"><code>tf.train.maybe_batch</code></a>
*   <a href="../../api_docs/python/tf/train/batch_join.md"><code>tf.train.batch_join</code></a>
*   <a href="../../api_docs/python/tf/train/maybe_batch_join.md"><code>tf.train.maybe_batch_join</code></a>
*   <a href="../../api_docs/python/tf/train/shuffle_batch.md"><code>tf.train.shuffle_batch</code></a>
*   <a href="../../api_docs/python/tf/train/maybe_shuffle_batch.md"><code>tf.train.maybe_shuffle_batch</code></a>
*   <a href="../../api_docs/python/tf/train/shuffle_batch_join.md"><code>tf.train.shuffle_batch_join</code></a>
*   <a href="../../api_docs/python/tf/train/maybe_shuffle_batch_join.md"><code>tf.train.maybe_shuffle_batch_join</code></a>
