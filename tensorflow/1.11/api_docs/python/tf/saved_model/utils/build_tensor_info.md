<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.saved_model.utils.build_tensor_info" />
<meta itemprop="path" content="Stable" />
</div>

# tf.saved_model.utils.build_tensor_info

``` python
tf.saved_model.utils.build_tensor_info(tensor)
```



Defined in [`tensorflow/python/saved_model/utils_impl.py`](https://www.tensorflow.org/code/tensorflow/python/saved_model/utils_impl.py).

Utility function to build TensorInfo proto.

#### Args:

* <b>`tensor`</b>: Tensor or SparseTensor whose name, dtype and shape are used to
      build the TensorInfo. For SparseTensors, the names of the three
      constitutent Tensors are used.


#### Returns:

A TensorInfo protocol buffer constructed based on the supplied argument.