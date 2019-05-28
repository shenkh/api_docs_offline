# Dataset Input Pipeline
[TOC]

<a href="../../api_docs/python/tf/data/Dataset.md"><code>tf.data.Dataset</code></a> allows you to build complex input pipelines. See the
<a href="../../guide/datasets.md">Importing Data</a> for an in-depth explanation of how to use this API.

<h2 id="Reader_classes">Reader classes</h2>

Classes that create a dataset from input files.

*   <a href="../../api_docs/python/tf/data/FixedLengthRecordDataset.md"><code>tf.data.FixedLengthRecordDataset</code></a>
*   <a href="../../api_docs/python/tf/data/TextLineDataset.md"><code>tf.data.TextLineDataset</code></a>
*   <a href="../../api_docs/python/tf/data/TFRecordDataset.md"><code>tf.data.TFRecordDataset</code></a>

<h2 id="Creating_new_datasets">Creating new datasets</h2>

Static methods in `Dataset` that create new datasets.

*   <a href="../../api_docs/python/tf/data/Dataset.md#from_generator"><code>tf.data.Dataset.from_generator</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#from_tensor_slices"><code>tf.data.Dataset.from_tensor_slices</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#from_tensors"><code>tf.data.Dataset.from_tensors</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#list_files"><code>tf.data.Dataset.list_files</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#range"><code>tf.data.Dataset.range</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#zip"><code>tf.data.Dataset.zip</code></a>

<h2 id="Transformations_on_existing_datasets">Transformations on existing datasets</h2>

These functions transform an existing dataset, and return a new dataset. Calls
can be chained together, as shown in the example below:

```
train_data = train_data.batch(100).shuffle().repeat()
```

*   <a href="../../api_docs/python/tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#batch"><code>tf.data.Dataset.batch</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#cache"><code>tf.data.Dataset.cache</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#concatenate"><code>tf.data.Dataset.concatenate</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#filter"><code>tf.data.Dataset.filter</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#flat_map"><code>tf.data.Dataset.flat_map</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#interleave"><code>tf.data.Dataset.interleave</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#map"><code>tf.data.Dataset.map</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#padded_batch"><code>tf.data.Dataset.padded_batch</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#prefetch"><code>tf.data.Dataset.prefetch</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#repeat"><code>tf.data.Dataset.repeat</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#shard"><code>tf.data.Dataset.shard</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#shuffle"><code>tf.data.Dataset.shuffle</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#skip"><code>tf.data.Dataset.skip</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#take"><code>tf.data.Dataset.take</code></a>

### Custom transformation functions

Custom transformation functions can be applied to a `Dataset` using <a href="../../api_docs/python/tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>. Below are custom transformation functions from <a href="../../api_docs/python/tf/contrib/data.md"><code>tf.contrib.data</code></a>:

*   <a href="../../api_docs/python/tf/contrib/data/batch_and_drop_remainder.md"><code>tf.contrib.data.batch_and_drop_remainder</code></a>
*   <a href="../../api_docs/python/tf/contrib/data/dense_to_sparse_batch.md"><code>tf.contrib.data.dense_to_sparse_batch</code></a>
*   <a href="../../api_docs/python/tf/contrib/data/enumerate_dataset.md"><code>tf.contrib.data.enumerate_dataset</code></a>
*   <a href="../../api_docs/python/tf/contrib/data/group_by_window.md"><code>tf.contrib.data.group_by_window</code></a>
*   <a href="../../api_docs/python/tf/contrib/data/ignore_errors.md"><code>tf.contrib.data.ignore_errors</code></a>
*   <a href="../../api_docs/python/tf/contrib/data/map_and_batch.md"><code>tf.contrib.data.map_and_batch</code></a>
*   <a href="../../api_docs/python/tf/contrib/data/padded_batch_and_drop_remainder.md"><code>tf.contrib.data.padded_batch_and_drop_remainder</code></a>
*   <a href="../../api_docs/python/tf/contrib/data/parallel_interleave.md"><code>tf.contrib.data.parallel_interleave</code></a>
*   <a href="../../api_docs/python/tf/contrib/data/rejection_resample.md"><code>tf.contrib.data.rejection_resample</code></a>
*   <a href="../../api_docs/python/tf/contrib/data/scan.md"><code>tf.contrib.data.scan</code></a>
*   <a href="../../api_docs/python/tf/contrib/data/shuffle_and_repeat.md"><code>tf.contrib.data.shuffle_and_repeat</code></a>
*   <a href="../../api_docs/python/tf/contrib/data/unbatch.md"><code>tf.contrib.data.unbatch</code></a>

<h2 id="Iterating_over_datasets">Iterating over datasets</h2>

These functions make a <a href="../../api_docs/python/tf/data/Iterator.md"><code>tf.data.Iterator</code></a> from a `Dataset`.

*   <a href="../../api_docs/python/tf/data/Dataset.md#make_initializable_iterator"><code>tf.data.Dataset.make_initializable_iterator</code></a>
*   <a href="../../api_docs/python/tf/data/Dataset.md#make_one_shot_iterator"><code>tf.data.Dataset.make_one_shot_iterator</code></a>

The `Iterator` class also contains static methods that create a <a href="../../api_docs/python/tf/data/Iterator.md"><code>tf.data.Iterator</code></a> that can be used with multiple `Dataset` objects.

*   <a href="../../api_docs/python/tf/data/Iterator.md#from_structure"><code>tf.data.Iterator.from_structure</code></a>
*   <a href="../../api_docs/python/tf/data/Iterator.md#from_string_handle"><code>tf.data.Iterator.from_string_handle</code></a>

<h2 id="Extra_functions_from_a_href_api_docs_python_tf_contrib_data_md_code_tf_contrib_data_code_a_">Extra functions from <a href="../../api_docs/python/tf/contrib/data.md"><code>tf.contrib.data</code></a></h2>

*   <a href="../../api_docs/python/tf/contrib/data/get_single_element.md"><code>tf.contrib.data.get_single_element</code></a>
*   <a href="../../api_docs/python/tf/contrib/data/make_saveable_from_iterator.md"><code>tf.contrib.data.make_saveable_from_iterator</code></a>
*   <a href="../../api_docs/python/tf/contrib/data/read_batch_features.md"><code>tf.contrib.data.read_batch_features</code></a>

