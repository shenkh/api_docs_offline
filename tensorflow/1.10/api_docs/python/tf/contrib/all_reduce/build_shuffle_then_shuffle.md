<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.all_reduce.build_shuffle_then_shuffle" />
</div>

# tf.contrib.all_reduce.build_shuffle_then_shuffle

``` python
tf.contrib.all_reduce.build_shuffle_then_shuffle(
    input_tensors,
    first_gather_devices,
    second_gather_devices,
    red_op,
    un_op=None
)
```



Defined in [`tensorflow/contrib/all_reduce/python/all_reduce.py`](https://www.tensorflow.org/code/tensorflow/contrib/all_reduce/python/all_reduce.py).

Construct hybrid of Shuffle within workers, Shuffle across workers.