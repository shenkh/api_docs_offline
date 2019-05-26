<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.opt.clip_gradients_by_global_norm" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.opt.clip_gradients_by_global_norm

``` python
tf.contrib.opt.clip_gradients_by_global_norm(
    gradients_variables,
    clip_norm=20.0
)
```



Defined in [`tensorflow/contrib/opt/python/training/multitask_optimizer_wrapper.py`](/code/stable/tensorflow/contrib/opt/python/training/multitask_optimizer_wrapper.py).

Clips gradients of a multitask loss by their global norm.

Ignores all-zero tensors when computing the global norm.

#### Args:

* <b>`gradients_variables`</b>: a list of pairs (gradient, variable).
* <b>`clip_norm`</b>: a float Tensor, the global norm to clip on. Default is 20.0.


#### Returns:

* <b>`list`</b>: A list of pairs of the same type as gradients_variables,.
* <b>`fixed_global_norm`</b>: A 0-D (scalar) Tensor representing the global norm.