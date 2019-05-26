<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.all_reduce.build_ring_all_reduce" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.all_reduce.build_ring_all_reduce

``` python
tf.contrib.all_reduce.build_ring_all_reduce(
    input_tensors,
    num_workers,
    num_subchunks,
    gpu_perm,
    red_op,
    un_op=None
)
```



Defined in [`tensorflow/contrib/all_reduce/python/all_reduce.py`](https://www.tensorflow.org/code/tensorflow/contrib/all_reduce/python/all_reduce.py).

Construct a subgraph performing a ring-style all-reduce of input_tensors.

#### Args:

* <b>`input_tensors`</b>: a list of T <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a> objects, which must all
    have the same shape and type.
* <b>`num_workers`</b>: number of worker tasks spanned by input_tensors.
* <b>`num_subchunks`</b>: number of subchunks each device should process in one tick.
* <b>`gpu_perm`</b>: a list of ints giving a ring-wise rank ordering of GPUs at
    each worker.  All workers must have the same number of
    GPUs with the same rank ordering.  If NVLINK is available, this should
    be a ring order supported by NVLINK edges.
* <b>`red_op`</b>: a binary operator for elementwise reduction.
* <b>`un_op`</b>: an optional unary operator to apply to fully reduced values.


#### Raises:

* <b>`ValueError`</b>: empty input_tensors or they don't all have same
  size.


#### Returns:

a list of T <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a> identical sum-reductions of input_tensors.