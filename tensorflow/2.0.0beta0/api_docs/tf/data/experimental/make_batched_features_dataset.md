<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.make_batched_features_dataset" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.make_batched_features_dataset



### Aliases:

* `tf.compat.v2.data.experimental.make_batched_features_dataset`
* `tf.data.experimental.make_batched_features_dataset`

``` python
tf.data.experimental.make_batched_features_dataset(
    file_pattern,
    batch_size,
    features,
    reader=tf.compat.v1.data.TFRecordDataset,
    label_key=None,
    reader_args=None,
    num_epochs=None,
    shuffle=True,
    shuffle_buffer_size=10000,
    shuffle_seed=None,
    prefetch_buffer_size=dataset_ops.AUTOTUNE,
    reader_num_threads=1,
    parser_num_threads=2,
    sloppy_ordering=False,
    drop_final_batch=False
)
```



Defined in [`python/data/experimental/ops/readers.py`](/code/stable/tensorflow/python/data/experimental/ops/readers.py).

<!-- Placeholder for "Used in" -->
