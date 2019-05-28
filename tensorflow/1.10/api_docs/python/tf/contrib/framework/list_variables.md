<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.list_variables" />
</div>

# tf.contrib.framework.list_variables

``` python
tf.contrib.framework.list_variables(checkpoint_dir)
```



Defined in [`tensorflow/contrib/framework/python/framework/checkpoint_utils.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/python/framework/checkpoint_utils.py).

See the guide: [Framework (contrib) > Checkpoint utilities](../../../../../api_guides/python/contrib.framework.md#Checkpoint_utilities)

Returns list of all variables in the latest checkpoint.

#### Args:

* <b>`checkpoint_dir`</b>: Directory with checkpoints file or path to checkpoint.


#### Returns:

List of tuples `(name, shape)`.