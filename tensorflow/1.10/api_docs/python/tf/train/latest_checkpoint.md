<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.latest_checkpoint" />
</div>

# tf.train.latest_checkpoint

``` python
tf.train.latest_checkpoint(
    checkpoint_dir,
    latest_filename=None
)
```



Defined in [`tensorflow/python/training/saver.py`](https://www.tensorflow.org/code/tensorflow/python/training/saver.py).

See the guide: [Variables > Saving and Restoring Variables](../../../../api_guides/python/state_ops.md#Saving_and_Restoring_Variables)

Finds the filename of latest saved checkpoint file.

#### Args:

* <b>`checkpoint_dir`</b>: Directory where the variables were saved.
* <b>`latest_filename`</b>: Optional name for the protocol buffer file that
    contains the list of most recent checkpoint filenames.
    See the corresponding argument to `Saver.save()`.


#### Returns:

The full path to the latest checkpoint or `None` if no checkpoint was found.