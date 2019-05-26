<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.gan.features.condition_tensor_from_onehot" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.gan.features.condition_tensor_from_onehot

``` python
tf.contrib.gan.features.condition_tensor_from_onehot(
    tensor,
    one_hot_labels,
    embedding_size=256
)
```



Defined in [`tensorflow/contrib/gan/python/features/python/conditioning_utils_impl.py`](/code/stable/tensorflow/contrib/gan/python/features/python/conditioning_utils_impl.py).

Condition a tensor based on a one-hot tensor.

Conditioning scheme based on https://arxiv.org/abs/1609.03499.

#### Args:

* <b>`tensor`</b>: Tensor to be conditioned.
* <b>`one_hot_labels`</b>: A Tensor of one-hot labels. Shape is
    [batch_size, num_classes].
* <b>`embedding_size`</b>: The size of the class embedding.


#### Returns:

`tensor` conditioned on `one_hot_labels`.


#### Raises:

* <b>`ValueError`</b>: `one_hot_labels` isn't 2D, if non-batch dimensions aren't
    fully defined, or if batch sizes don't match.