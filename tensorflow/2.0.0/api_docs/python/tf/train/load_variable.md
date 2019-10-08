<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.load_variable" />
<meta itemprop="path" content="Stable" />
</div>

# tf.train.load_variable

``` python
tf.train.load_variable(
    ckpt_dir_or_file,
    name
)
```



Defined in [`tensorflow/python/training/checkpoint_utils.py`](/code/stable/tensorflow/python/training/checkpoint_utils.py).

Returns the tensor value of the given variable in the checkpoint.

#### Args:

* <b>`ckpt_dir_or_file`</b>: Directory with checkpoints file or path to checkpoint.
* <b>`name`</b>: Name of the variable to return.


#### Returns:

A numpy `ndarray` with a copy of the value of this variable.