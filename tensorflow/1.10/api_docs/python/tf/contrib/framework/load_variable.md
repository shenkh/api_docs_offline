<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.load_variable" />
</div>

# tf.contrib.framework.load_variable

``` python
tf.contrib.framework.load_variable(
    checkpoint_dir,
    name
)
```



Defined in [`tensorflow/contrib/framework/python/framework/checkpoint_utils.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/python/framework/checkpoint_utils.py).

See the guide: [Framework (contrib) > Checkpoint utilities](../../../../../api_guides/python/contrib.framework.md#Checkpoint_utilities)

Returns a Tensor with the contents of the given variable in the checkpoint.

#### Args:

* <b>`checkpoint_dir`</b>: Directory with checkpoints file or path to checkpoint.
* <b>`name`</b>: Name of the tensor to return.


#### Returns:

`Tensor` object.