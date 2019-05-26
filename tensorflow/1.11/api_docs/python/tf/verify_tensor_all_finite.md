<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.verify_tensor_all_finite" />
<meta itemprop="path" content="Stable" />
</div>

# tf.verify_tensor_all_finite

``` python
tf.verify_tensor_all_finite(
    t,
    msg,
    name=None
)
```



Defined in [`tensorflow/python/ops/numerics.py`](https://www.tensorflow.org/code/tensorflow/python/ops/numerics.py).

Assert that the tensor does not contain any NaN's or Inf's.

#### Args:

* <b>`t`</b>: Tensor to check.
* <b>`msg`</b>: Message to log on failure.
* <b>`name`</b>: A name for this operation (optional).


#### Returns:

Same tensor as `t`.