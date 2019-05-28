<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.softmax_cross_entropy_with_logits" />
</div>

# tf.nn.softmax_cross_entropy_with_logits

``` python
tf.nn.softmax_cross_entropy_with_logits(
    _sentinel=None,
    labels=None,
    logits=None,
    dim=-1,
    name=None
)
```



Defined in [`tensorflow/python/ops/nn_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/nn_ops.py).

See the guide: [Neural Network > Classification](../../../../api_guides/python/nn.md#Classification)

Computes softmax cross entropy between `logits` and `labels`. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:

Future major versions of TensorFlow will allow gradients to flow
into the labels input on backprop by default.

See <a href="../../tf/nn/softmax_cross_entropy_with_logits_v2.md"><code>tf.nn.softmax_cross_entropy_with_logits_v2</code></a>.


Measures the probability error in discrete classification tasks in which the
classes are mutually exclusive (each entry is in exactly one class).  For
example, each CIFAR-10 image is labeled with one and only one label: an image
can be a dog or a truck, but not both.

**NOTE:**  While the classes are mutually exclusive, their probabilities
need not be.  All that is required is that each row of `labels` is
a valid probability distribution.  If they are not, the computation of the
gradient will be incorrect.

If using exclusive `labels` (wherein one and only
one class is true at a time), see `sparse_softmax_cross_entropy_with_logits`.

**WARNING:** This op expects unscaled logits, since it performs a `softmax`
on `logits` internally for efficiency.  Do not call this op with the
output of `softmax`, as it will produce incorrect results.

A common use case is to have logits and labels of shape
`[batch_size, num_classes]`, but higher dimensions are supported, with
the `dim` argument specifying the class dimension.

Backpropagation will happen only into `logits`.  To calculate a cross entropy
loss that allows backpropagation into both `logits` and `labels`, see
<a href="../../tf/nn/softmax_cross_entropy_with_logits_v2.md"><code>tf.nn.softmax_cross_entropy_with_logits_v2</code></a>.

**Note that to avoid confusion, it is required to pass only named arguments to
this function.**

#### Args:

* <b>`_sentinel`</b>: Used to prevent positional parameters. Internal, do not use.
* <b>`labels`</b>: Each vector along the class dimension should hold a valid
    probability distribution e.g. for the case in which labels are of shape
    `[batch_size, num_classes]`, each row of `labels[i]` must be a valid
    probability distribution.
* <b>`logits`</b>: Unscaled log probabilities.
* <b>`dim`</b>: The class dimension. Defaulted to -1 which is the last dimension.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of the same shape as `labels` and of the same type as `logits`
with the softmax cross entropy loss.