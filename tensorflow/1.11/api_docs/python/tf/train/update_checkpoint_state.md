<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.update_checkpoint_state" />
<meta itemprop="path" content="Stable" />
</div>

# tf.train.update_checkpoint_state

``` python
tf.train.update_checkpoint_state(
    save_dir,
    model_checkpoint_path,
    all_model_checkpoint_paths=None,
    latest_filename=None,
    all_model_checkpoint_timestamps=None,
    last_preserved_timestamp=None
)
```



Defined in [`tensorflow/python/training/checkpoint_management.py`](https://www.tensorflow.org/code/tensorflow/python/training/checkpoint_management.py).

Updates the content of the 'checkpoint' file.

This updates the checkpoint file containing a CheckpointState
proto.

#### Args:

* <b>`save_dir`</b>: Directory where the model was saved.
* <b>`model_checkpoint_path`</b>: The checkpoint file.
* <b>`all_model_checkpoint_paths`</b>: List of strings.  Paths to all not-yet-deleted
    checkpoints, sorted from oldest to newest.  If this is a non-empty list,
    the last element must be equal to model_checkpoint_path.  These paths
    are also saved in the CheckpointState proto.
* <b>`latest_filename`</b>: Optional name of the checkpoint file.  Default to
    'checkpoint'.
* <b>`all_model_checkpoint_timestamps`</b>: Optional list of timestamps (floats,
    seconds since the Epoch) indicating when the checkpoints in
    `all_model_checkpoint_paths` were created.
* <b>`last_preserved_timestamp`</b>: A float, indicating the number of seconds since
    the Epoch when the last preserved checkpoint was written, e.g. due to a
    `keep_checkpoint_every_n_hours` parameter (see
    <a href="../../tf/contrib/checkpoint/CheckpointManager.md"><code>tf.contrib.checkpoint.CheckpointManager</code></a> for an implementation).

#### Raises:

* <b>`RuntimeError`</b>: If any of the model checkpoint paths conflict with the file
    containing CheckpointSate.