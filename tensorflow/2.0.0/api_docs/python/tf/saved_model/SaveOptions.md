<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.saved_model.SaveOptions" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="namespace_whitelist"/>
</div>

# tf.saved_model.SaveOptions

## Class `SaveOptions`





Defined in [`tensorflow/python/saved_model/save_options.py`](/code/stable/tensorflow/python/saved_model/save_options.py).

Options for saving to SavedModel.

This function may be used in the `options` argument in functions that
save a SavedModel (<a href="../../tf/saved_model/save.md"><code>tf.saved_model.save</code></a>, <a href="../../tf/keras/models/save_model.md"><code>tf.keras.models.save_model</code></a>).

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(namespace_whitelist=None)
```

Creates an object that stores options for SavedModel saving.

#### Args:

* <b>`namespace_whitelist`</b>: List of strings containing op namespaces to whitelist
    when saving a model. Saving an object that uses namespaced ops must
    explicitly add all namespaces to the whitelist. The namespaced ops must
    be registered into the framework when loading the SavedModel.



## Class Members

<h3 id="namespace_whitelist"><code>namespace_whitelist</code></h3>

