<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.assert_global_step" />
</div>

# tf.train.assert_global_step

``` python
tf.train.assert_global_step(global_step_tensor)
```



Defined in [`tensorflow/python/training/training_util.py`](https://www.tensorflow.org/code/tensorflow/python/training/training_util.py).

See the guides: [Framework (contrib) > Variables](../../../../api_guides/python/contrib.framework.md#Variables), [Training > Training Utilities](../../../../api_guides/python/train.md#Training_Utilities)

Asserts `global_step_tensor` is a scalar int `Variable` or `Tensor`.

#### Args:

* <b>`global_step_tensor`</b>: `Tensor` to test.