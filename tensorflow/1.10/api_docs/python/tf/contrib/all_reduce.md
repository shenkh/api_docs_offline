<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.all_reduce" />
</div>

# Module: tf.contrib.all_reduce



Defined in [`tensorflow/contrib/all_reduce/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/all_reduce/__init__.py).

All-reduce implementations.

## Functions

[`build_nccl_all_reduce(...)`](../../tf/contrib/all_reduce/build_nccl_all_reduce.md): Build a subgraph that does one full all-reduce, using NCCL.

[`build_nccl_then_recursive_hd(...)`](../../tf/contrib/all_reduce/build_nccl_then_recursive_hd.md): Construct hybrid of NCCL within workers, Recursive-HD across workers.

[`build_nccl_then_ring(...)`](../../tf/contrib/all_reduce/build_nccl_then_ring.md): Construct hybrid of NCCL within workers, Ring across workers.

[`build_nccl_then_shuffle(...)`](../../tf/contrib/all_reduce/build_nccl_then_shuffle.md): Construct hybrid of NCCL within workers, Shuffle across workers.

[`build_recursive_hd_all_reduce(...)`](../../tf/contrib/all_reduce/build_recursive_hd_all_reduce.md): Construct a subgraph for recursive halving-doubling all-reduce.

[`build_ring_all_reduce(...)`](../../tf/contrib/all_reduce/build_ring_all_reduce.md): Construct a subgraph performing a ring-style all-reduce of input_tensors.

[`build_shuffle_all_reduce(...)`](../../tf/contrib/all_reduce/build_shuffle_all_reduce.md): Construct a subgraph for shuffle all-reduce.

[`build_shuffle_then_ring(...)`](../../tf/contrib/all_reduce/build_shuffle_then_ring.md): Construct hybrid of Shuffle within workers, Ring across workers.

[`build_shuffle_then_shuffle(...)`](../../tf/contrib/all_reduce/build_shuffle_then_shuffle.md): Construct hybrid of Shuffle within workers, Shuffle across workers.

