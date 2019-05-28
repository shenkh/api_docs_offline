<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.applications.densenet.preprocess_input" />
</div>

# tf.keras.applications.densenet.preprocess_input

``` python
tf.keras.applications.densenet.preprocess_input(
    x,
    data_format=None
)
```



Defined in [`tensorflow/python/keras/applications/densenet.py`](https://www.tensorflow.org/code/tensorflow/python/keras/applications/densenet.py).

Preprocesses a numpy array encoding a batch of images.

#### Arguments:

* <b>`x`</b>: a 3D or 4D numpy array consists of RGB values within [0, 255].
* <b>`data_format`</b>: data format of the image tensor.


#### Returns:

Preprocessed array.