<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.data.make_saveable_from_iterator" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.data.make_saveable_from_iterator

``` python
tf.contrib.data.make_saveable_from_iterator(iterator)
```



Defined in [`tensorflow/contrib/data/python/ops/iterator_ops.py`](/code/stable/tensorflow/contrib/data/python/ops/iterator_ops.py).

Returns a SaveableObject for saving/restore iterator state using Saver. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.data.experimental.make_saveable_from_iterator(...)`.

#### Args:

* <b>`iterator`</b>: Iterator.

For example:

```python
with tf.Graph().as_default():
  ds = tf.data.Dataset.range(10)
  iterator = ds.make_initializable_iterator()
  # Build the iterator SaveableObject.
  saveable_obj = tf.contrib.data.make_saveable_from_iterator(iterator)
  # Add the SaveableObject to the SAVEABLE_OBJECTS collection so
  # it can be automatically saved using Saver.
  tf.add_to_collection(tf.GraphKeys.SAVEABLE_OBJECTS, saveable_obj)
  saver = tf.train.Saver()

  while continue_training:
    ... Perform training ...
    if should_save_checkpoint:
      saver.save()
```

Note: When restoring the iterator, the existing iterator state is completely
discarded. This means that any changes you may have made to the Dataset
graph will be discarded as well! This includes the new Dataset graph
that you may have built during validation. So, while running validation,
make sure to run the initializer for the validation input pipeline after
restoring the checkpoint.

Note: Not all iterators support checkpointing yet. Attempting to save the
state of an unsupported iterator will throw an error.