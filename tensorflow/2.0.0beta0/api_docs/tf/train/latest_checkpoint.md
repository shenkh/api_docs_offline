<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.latest_checkpoint" />
<meta itemprop="path" content="Stable" />
</div>

# tf.train.latest_checkpoint

Finds the filename of latest saved checkpoint file.

### Aliases:

* `tf.compat.v1.train.latest_checkpoint`
* `tf.compat.v2.train.latest_checkpoint`
* `tf.train.latest_checkpoint`

``` python
tf.train.latest_checkpoint(
    checkpoint_dir,
    latest_filename=None
)
```



Defined in [`python/training/checkpoint_management.py`](/code/stable/tensorflow/python/training/checkpoint_management.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`checkpoint_dir`</b>: Directory where the variables were saved.
* <b>`latest_filename`</b>: Optional name for the protocol buffer file that
  contains the list of most recent checkpoint filenames.
  See the corresponding argument to `Saver.save()`.


#### Returns:

The full path to the latest checkpoint or `None` if no checkpoint was found.
