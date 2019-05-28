<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.model_pruning.apply_mask" />
</div>

# tf.contrib.model_pruning.apply_mask

``` python
tf.contrib.model_pruning.apply_mask(
    x,
    scope=''
)
```



Defined in [`tensorflow/contrib/model_pruning/python/pruning.py`](https://www.tensorflow.org/code/tensorflow/contrib/model_pruning/python/pruning.py).

Apply mask to a given weight tensor.

#### Args:

* <b>`x`</b>: Input weight tensor
* <b>`scope`</b>: The current variable scope. Defaults to "".

#### Returns:

Tensor representing masked_weights