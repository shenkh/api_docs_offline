<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.callbacks.Callback" />
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

# tf.keras.callbacks.Callback

## Class `Callback`





Defined in [`tensorflow/python/keras/callbacks.py`](https://www.tensorflow.org/code/tensorflow/python/keras/callbacks.py).

Abstract base class used to build new callbacks.

#### Attributes:

* <b>`params`</b>: dict. Training parameters
        (eg. verbosity, batch size, number of epochs...).
* <b>`model`</b>: instance of `keras.models.Model`.
        Reference of the model being trained.

The `logs` dictionary that callback methods
take as argument will contain keys for quantities relevant to
the current batch or epoch.

Currently, the `.fit()` method of the `Sequential` model class
will include the following quantities in the `logs` that
it passes to its callbacks:

* <b>`on_epoch_end`</b>: logs include `acc` and `loss`, and
        optionally include `val_loss`
        (if validation is enabled in `fit`), and `val_acc`
        (if validation and accuracy monitoring are enabled).
* <b>`on_batch_begin`</b>: logs include `size`,
        the number of samples in the current batch.
* <b>`on_batch_end`</b>: logs include `loss`, and optionally `acc`
        (if accuracy monitoring is enabled).

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__()
```

Initialize self.  See help(type(self)) for accurate signature.

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





