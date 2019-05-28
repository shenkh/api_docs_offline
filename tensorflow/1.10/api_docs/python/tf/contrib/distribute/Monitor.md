<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distribute.Monitor" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="run_steps"/>
</div>

# tf.contrib.distribute.Monitor

## Class `Monitor`





Defined in [`tensorflow/contrib/distribute/python/monitor.py`](https://www.tensorflow.org/code/tensorflow/contrib/distribute/python/monitor.py).

Executes training steps, recovers and checkpoints.

Note that this class is particularly preliminary, experimental, and
expected to change.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    step_callable,
    session=None
)
```

Initialize the Monitor with components for executing training steps.

#### Args:

* <b>`step_callable`</b>: a training `Step` that's capable of signaling when done.
* <b>`session`</b>: a `Session` instance that's needed for graph mode.


#### Raises:

* <b>`ValueError`</b>: if `session` was provided for eager mode or not provided for
    graph mode.

<h3 id="run_steps"><code>run_steps</code></h3>

``` python
run_steps(num_steps=None)
```





