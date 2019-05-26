<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.test.is_gpu_available" />
<meta itemprop="path" content="Stable" />
</div>

# tf.test.is_gpu_available

``` python
tf.test.is_gpu_available(
    cuda_only=False,
    min_cuda_compute_capability=None
)
```



Defined in [`tensorflow/python/framework/test_util.py`](/code/stable/tensorflow/python/framework/test_util.py).

Returns whether TensorFlow can access a GPU.

#### Args:

* <b>`cuda_only`</b>: limit the search to CUDA gpus.
* <b>`min_cuda_compute_capability`</b>: a (major,minor) pair that indicates the minimum
    CUDA compute capability required, or None if no requirement.


#### Returns:

True iff a gpu device of the requested kind is available.