<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.all_reduce.build_nccl_then_ring" />
</div>

# tf.contrib.all_reduce.build_nccl_then_ring

``` python
tf.contrib.all_reduce.build_nccl_then_ring(
    input_tensors,
    subdiv,
    red_op,
    un_op=None
)
```



Defined in [`tensorflow/contrib/all_reduce/python/all_reduce.py`](https://www.tensorflow.org/code/tensorflow/contrib/all_reduce/python/all_reduce.py).

Construct hybrid of NCCL within workers, Ring across workers.