<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.all_reduce.build_nccl_all_reduce" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.all_reduce.build_nccl_all_reduce

``` python
tf.contrib.all_reduce.build_nccl_all_reduce(
    input_tensors,
    red_op,
    un_op=None
)
```



Defined in [`tensorflow/contrib/all_reduce/python/all_reduce.py`](/code/stable/tensorflow/contrib/all_reduce/python/all_reduce.py).

Build a subgraph that does one full all-reduce, using NCCL.

#### Args:

* <b>`input_tensors`</b>: list of T <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a> of same-shape and type values to
    be reduced.
* <b>`red_op`</b>: binary elementwise reduction operator.  Must be one of
    {tf.add}
* <b>`un_op`</b>: optional unary elementwise Op to apply to fully-reduce values.


#### Returns:

list of T <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a> of reduced values.


#### Raises:

* <b>`ValueError`</b>: red_op not supported.