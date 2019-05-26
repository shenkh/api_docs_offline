<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.data.experimental



Defined in [`tensorflow/_api/v1/data/experimental/__init__.py`](/code/stable/tensorflow/_api/v1/data/experimental/__init__.py).

Experimental API for building input pipelines.

This module contains experimental `Dataset` sources and transformations that can
be used in conjunction with the <a href="../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> API. Note that the
<a href="../../tf/data/experimental.md"><code>tf.data.experimental</code></a> API is not subject to the same backwards compatibility
guarantees as <a href="../../tf/data.md"><code>tf.data</code></a>, but we will provide deprecation advice in advance of
removing existing functionality.

See [Importing Data](https://tensorflow.org/guide/datasets) for an overview.



## Classes

[`class CheckpointInputPipelineHook`](../../tf/data/experimental/CheckpointInputPipelineHook.md): Checkpoints input pipeline state every N steps or seconds.

[`class CsvDataset`](../../tf/data/experimental/CsvDataset.md): A Dataset comprising lines from one or more CSV files.

[`class Optional`](../../tf/data/experimental/Optional.md): Wraps a nested structure of tensors that may/may not be present at runtime.

[`class RandomDataset`](../../tf/data/experimental/RandomDataset.md): A `Dataset` of pseudorandom values.

[`class Reducer`](../../tf/data/experimental/Reducer.md): A reducer is used for reducing a set of elements.

[`class SqlDataset`](../../tf/data/experimental/SqlDataset.md): A `Dataset` consisting of the results from a SQL query.

[`class StatsAggregator`](../../tf/data/experimental/StatsAggregator.md): A stateful resource that aggregates statistics from one or more iterators.

[`class TFRecordWriter`](../../tf/data/experimental/TFRecordWriter.md): Writes data to a TFRecord file.

## Functions

[`Counter(...)`](../../tf/data/experimental/Counter.md): Creates a `Dataset` that counts from `start` in steps of size `step`.

[`bucket_by_sequence_length(...)`](../../tf/data/experimental/bucket_by_sequence_length.md): A transformation that buckets elements in a `Dataset` by length.

[`choose_from_datasets(...)`](../../tf/data/experimental/choose_from_datasets.md): Creates a dataset that deterministically chooses elements from `datasets`.

[`copy_to_device(...)`](../../tf/data/experimental/copy_to_device.md): A transformation that copies dataset elements to the given `target_device`.

[`dense_to_sparse_batch(...)`](../../tf/data/experimental/dense_to_sparse_batch.md): A transformation that batches ragged elements into <a href="../../tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a>s.

[`enumerate_dataset(...)`](../../tf/data/experimental/enumerate_dataset.md): A transformation that enumerate the elements of a dataset.

[`get_next_as_optional(...)`](../../tf/data/experimental/get_next_as_optional.md): Returns an `Optional` that contains the next value from the iterator.

[`get_single_element(...)`](../../tf/data/experimental/get_single_element.md): Returns the single element in `dataset` as a nested structure of tensors.

[`group_by_reducer(...)`](../../tf/data/experimental/group_by_reducer.md): A transformation that groups elements and performs a reduction.

[`group_by_window(...)`](../../tf/data/experimental/group_by_window.md): A transformation that groups windows of elements by key and reduces them.

[`ignore_errors(...)`](../../tf/data/experimental/ignore_errors.md): Creates a `Dataset` from another `Dataset` and silently ignores any errors.

[`latency_stats(...)`](../../tf/data/experimental/latency_stats.md): Records the latency of producing each element of the input dataset.

[`make_batched_features_dataset(...)`](../../tf/data/experimental/make_batched_features_dataset.md): Returns a `Dataset` of feature dictionaries from `Example` protos.

[`make_csv_dataset(...)`](../../tf/data/experimental/make_csv_dataset.md): Reads CSV files into a dataset.

[`make_saveable_from_iterator(...)`](../../tf/data/experimental/make_saveable_from_iterator.md): Returns a SaveableObject for saving/restore iterator state using Saver.

[`map_and_batch(...)`](../../tf/data/experimental/map_and_batch.md): Fused implementation of `map` and `batch`.

[`parallel_interleave(...)`](../../tf/data/experimental/parallel_interleave.md): A parallel version of the `Dataset.interleave()` transformation.

[`parse_example_dataset(...)`](../../tf/data/experimental/parse_example_dataset.md): A transformation that parses `Example` protos into a `dict` of tensors.

[`prefetch_to_device(...)`](../../tf/data/experimental/prefetch_to_device.md): A transformation that prefetches dataset values to the given `device`.

[`rejection_resample(...)`](../../tf/data/experimental/rejection_resample.md): A transformation that resamples a dataset to achieve a target distribution.

[`sample_from_datasets(...)`](../../tf/data/experimental/sample_from_datasets.md): Samples elements at random from the datasets in `datasets`.

[`scan(...)`](../../tf/data/experimental/scan.md): A transformation that scans a function across an input dataset.

[`set_stats_aggregator(...)`](../../tf/data/experimental/set_stats_aggregator.md): Set the given `stats_aggregator` for aggregating the input dataset stats.

[`shuffle_and_repeat(...)`](../../tf/data/experimental/shuffle_and_repeat.md): Shuffles and repeats a Dataset returning a new permutation for each epoch.

[`unbatch(...)`](../../tf/data/experimental/unbatch.md): Splits elements of a dataset into multiple elements on the batch dimension.

[`unique(...)`](../../tf/data/experimental/unique.md): Creates a `Dataset` from another `Dataset`, discarding duplicates.

