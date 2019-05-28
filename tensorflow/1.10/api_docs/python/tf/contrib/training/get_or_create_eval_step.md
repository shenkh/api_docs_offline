<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.training.get_or_create_eval_step" />
</div>

# tf.contrib.training.get_or_create_eval_step

``` python
tf.contrib.training.get_or_create_eval_step()
```



Defined in [`tensorflow/python/training/evaluation.py`](https://www.tensorflow.org/code/tensorflow/python/training/evaluation.py).

Gets or creates the eval step `Tensor`.

#### Returns:

A `Tensor` representing a counter for the evaluation step.


#### Raises:

* <b>`ValueError`</b>: If multiple `Tensors` have been added to the
    <a href="../../../tf/GraphKeys.md#EVAL_STEP"><code>tf.GraphKeys.EVAL_STEP</code></a> collection.