<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.callbacks.ProgbarLogger" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="on_batch_begin"/>
<meta itemprop="property" content="on_batch_end"/>
<meta itemprop="property" content="on_epoch_begin"/>
<meta itemprop="property" content="on_epoch_end"/>
<meta itemprop="property" content="on_train_begin"/>
<meta itemprop="property" content="on_train_end"/>
<meta itemprop="property" content="set_model"/>
<meta itemprop="property" content="set_params"/>
</div>

# tf.keras.callbacks.ProgbarLogger

## Class `ProgbarLogger`

Inherits From: [`Callback`](../../../tf/keras/callbacks/Callback.md)



Defined in [`tensorflow/python/keras/callbacks.py`](https://www.tensorflow.org/code/tensorflow/python/keras/callbacks.py).

Callback that prints metrics to stdout.

#### Arguments:

* <b>`count_mode`</b>: One of "steps" or "samples".
        Whether the progress bar should
        count samples seen or steps (batches) seen.
* <b>`stateful_metrics`</b>: Iterable of string names of metrics that
        should *not* be averaged over an epoch.
        Metrics in this list will be logged as-is.
        All others will be averaged over time (e.g. loss, etc).


#### Raises:

* <b>`ValueError`</b>: In case of invalid `count_mode`.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    count_mode='samples',
    stateful_metrics=None
)
```

Initialize self.  See help(type(self)) for accurate signature.



## Methods

<h3 id="on_batch_begin"><code>on_batch_begin</code></h3>

``` python
on_batch_begin(
    batch,
    logs=None
)
```



<h3 id="on_batch_end"><code>on_batch_end</code></h3>

``` python
on_batch_end(
    batch,
    logs=None
)
```



<h3 id="on_epoch_begin"><code>on_epoch_begin</code></h3>

``` python
on_epoch_begin(
    epoch,
    logs=None
)
```



<h3 id="on_epoch_end"><code>on_epoch_end</code></h3>

``` python
on_epoch_end(
    epoch,
    logs=None
)
```



<h3 id="on_train_begin"><code>on_train_begin</code></h3>

``` python
on_train_begin(logs=None)
```



<h3 id="on_train_end"><code>on_train_end</code></h3>

``` python
on_train_end(logs=None)
```



<h3 id="set_model"><code>set_model</code></h3>

``` python
set_model(model)
```



<h3 id="set_params"><code>set_params</code></h3>

``` python
set_params(params)
```





