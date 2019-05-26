<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.saved_model.load_keras_model" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.saved_model.load_keras_model

``` python
tf.contrib.saved_model.load_keras_model(saved_model_path)
```



Defined in [`tensorflow/contrib/saved_model/python/saved_model/keras_saved_model.py`](https://www.tensorflow.org/code/tensorflow/contrib/saved_model/python/saved_model/keras_saved_model.py).

Load a keras.Model from SavedModel.

load_model reinstantiates model state by:
1) loading model topology from json (this will eventually come
   from metagraph).
2) loading model weights from checkpoint.

#### Args:

* <b>`saved_model_path`</b>: a string specifying the path to an existing SavedModel.


#### Returns:

a keras.Model instance.