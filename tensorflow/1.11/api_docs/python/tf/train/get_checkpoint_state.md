<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.get_checkpoint_state" />
<meta itemprop="path" content="Stable" />
</div>

# tf.train.get_checkpoint_state

``` python
tf.train.get_checkpoint_state(
    checkpoint_dir,
    latest_filename=None
)
```



Defined in [`tensorflow/python/training/checkpoint_management.py`](https://www.tensorflow.org/code/tensorflow/python/training/checkpoint_management.py).

Returns CheckpointState proto from the "checkpoint" file.

If the "checkpoint" file contains a valid CheckpointState
proto, returns it.

#### Args:

* <b>`checkpoint_dir`</b>: The directory of checkpoints.
* <b>`latest_filename`</b>: Optional name of the checkpoint file.  Default to
    'checkpoint'.


#### Returns:

A CheckpointState if the state was available, None
otherwise.


#### Raises:

* <b>`ValueError`</b>: if the checkpoint read doesn't have model_checkpoint_path set.