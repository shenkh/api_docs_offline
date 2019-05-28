<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.linear_cosine_decay" />
</div>

# tf.train.linear_cosine_decay

``` python
tf.train.linear_cosine_decay(
    learning_rate,
    global_step,
    decay_steps,
    num_periods=0.5,
    alpha=0.0,
    beta=0.001,
    name=None
)
```



Defined in [`tensorflow/python/training/learning_rate_decay.py`](https://www.tensorflow.org/code/tensorflow/python/training/learning_rate_decay.py).

See the guide: [Training > Decaying the learning rate](../../../../api_guides/python/train.md#Decaying_the_learning_rate)

Applies linear cosine decay to the learning rate.

See [Bello et al., ICML2017] Neural Optimizer Search with RL.
https://arxiv.org/abs/1709.07417

For the idea of warm starts here controlled by `num_periods`,
see [Loshchilov & Hutter, ICLR2016] SGDR: Stochastic Gradient Descent
with Warm Restarts. https://arxiv.org/abs/1608.03983

Note that linear cosine decay is more aggressive than cosine decay and
larger initial learning rates can typically be used.

When training a model, it is often recommended to lower the learning rate as
the training progresses.  This function applies a linear cosine decay function
to a provided initial learning rate.  It requires a `global_step` value to
compute the decayed learning rate.  You can just pass a TensorFlow variable
that you increment at each training step.

The function returns the decayed learning rate.  It is computed as:
```python
global_step = min(global_step, decay_steps)
linear_decay = (decay_steps - global_step) / decay_steps)
cosine_decay = 0.5 * (
    1 + cos(pi * 2 * num_periods * global_step / decay_steps))
decayed = (alpha + linear_decay) * cosine_decay + beta
decayed_learning_rate = learning_rate * decayed
```

Example usage:
```python
decay_steps = 1000
lr_decayed = linear_cosine_decay(learning_rate, global_step, decay_steps)
```

#### Args:

* <b>`learning_rate`</b>: A scalar `float32` or `float64` Tensor or a Python number.
    The initial learning rate.
* <b>`global_step`</b>: A scalar `int32` or `int64` `Tensor` or a Python number.
    Global step to use for the decay computation.
* <b>`decay_steps`</b>: A scalar `int32` or `int64` `Tensor` or a Python number.
    Number of steps to decay over.
* <b>`num_periods`</b>: Number of periods in the cosine part of the decay.
    See computation above.
* <b>`alpha`</b>: See computation above.
* <b>`beta`</b>: See computation above.
* <b>`name`</b>: String.  Optional name of the operation.  Defaults to
    'LinearCosineDecay'.

#### Returns:

A scalar `Tensor` of the same type as `learning_rate`.  The decayed
learning rate.

#### Raises:

* <b>`ValueError`</b>: if `global_step` is not supplied.



#### Eager Compatibility
When eager execution is enabled, this function returns a function which in
turn returns the decayed learning rate Tensor. This can be useful for changing
the learning rate value across different invocations of optimizer functions.

