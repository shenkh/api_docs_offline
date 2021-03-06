<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.models.save_model" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.models.save_model

``` python
tf.keras.models.save_model(
    model,
    filepath,
    overwrite=True,
    include_optimizer=True
)
```



Defined in [`tensorflow/python/keras/engine/saving.py`](https://www.tensorflow.org/code/tensorflow/python/keras/engine/saving.py).

Saves a model to a HDF5 file.

The saved model contains:
    - the model's configuration (topology)
    - the model's weights
    - the model's optimizer's state (if any)

Thus the saved model can be reinstantiated in
the exact same state, without any of the code
used for model definition or training.

#### Arguments:

* <b>`model`</b>: Keras model instance to be saved.
* <b>`filepath`</b>: One of the following:
        - String, path where to save the model
        - `h5py.File` object where to save the model
* <b>`overwrite`</b>: Whether we should overwrite any existing
        model at the target location, or instead
        ask the user with a manual prompt.
* <b>`include_optimizer`</b>: If True, save optimizer's state together.


#### Raises:

* <b>`ImportError`</b>: if h5py is not available.