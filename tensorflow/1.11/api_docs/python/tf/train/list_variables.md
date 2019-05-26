<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.list_variables" />
<meta itemprop="path" content="Stable" />
</div>

# tf.train.list_variables

``` python
tf.train.list_variables(ckpt_dir_or_file)
```



Defined in [`tensorflow/python/training/checkpoint_utils.py`](https://www.tensorflow.org/code/tensorflow/python/training/checkpoint_utils.py).

Returns list of all variables in the checkpoint.

#### Args:

* <b>`ckpt_dir_or_file`</b>: Directory with checkpoints file or path to checkpoint.


#### Returns:

List of tuples `(name, shape)`.