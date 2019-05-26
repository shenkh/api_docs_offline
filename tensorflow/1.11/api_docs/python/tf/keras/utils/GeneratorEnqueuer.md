<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.utils.GeneratorEnqueuer" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get"/>
<meta itemprop="property" content="is_running"/>
<meta itemprop="property" content="start"/>
<meta itemprop="property" content="stop"/>
</div>

# tf.keras.utils.GeneratorEnqueuer

## Class `GeneratorEnqueuer`

Inherits From: [`SequenceEnqueuer`](../../../tf/keras/utils/SequenceEnqueuer.md)



Defined in [`tensorflow/python/keras/utils/data_utils.py`](https://www.tensorflow.org/code/tensorflow/python/keras/utils/data_utils.py).

Builds a queue out of a data generator.

The provided generator can be finite in which case the class will throw
a `StopIteration` exception.

Used in `fit_generator`, `evaluate_generator`, `predict_generator`.

#### Arguments:

* <b>`generator`</b>: a generator function which yields data
* <b>`use_multiprocessing`</b>: use multiprocessing if True, otherwise threading
* <b>`wait_time`</b>: time to sleep in-between calls to `put()`
* <b>`random_seed`</b>: Initial seed for workers,
        will be incremented by one for each worker.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    generator,
    use_multiprocessing=False,
    wait_time=0.05,
    seed=None
)
```

Initialize self.  See help(type(self)) for accurate signature.



## Methods

<h3 id="get"><code>get</code></h3>

``` python
get()
```

Creates a generator to extract data from the queue.

Skip the data if it is `None`.

#### Yields:

The next element in the queue, i.e. a tuple
`(inputs, targets)` or
`(inputs, targets, sample_weights)`.

<h3 id="is_running"><code>is_running</code></h3>

``` python
is_running()
```



<h3 id="start"><code>start</code></h3>

``` python
start(
    workers=1,
    max_queue_size=10
)
```

Kicks off threads which add data from the generator into the queue.

#### Arguments:

* <b>`workers`</b>: number of worker threads
* <b>`max_queue_size`</b>: queue size
        (when full, threads could block on `put()`)

<h3 id="stop"><code>stop</code></h3>

``` python
stop(timeout=None)
```

Stops running threads and wait for them to exit, if necessary.

Should be called by the same thread which called `start()`.

#### Arguments:

* <b>`timeout`</b>: maximum time to wait on `thread.join()`.



