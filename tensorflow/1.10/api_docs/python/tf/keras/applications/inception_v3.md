<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.applications.inception_v3" />
</div>

# Module: tf.keras.applications.inception_v3



Defined in [`tensorflow/keras/applications/inception_v3/__init__.py`](https://www.tensorflow.org/code/tensorflow/keras/applications/inception_v3/__init__.py).

Inception V3 model for Keras.

Note that the input image format for this model is different than for
the VGG16 and ResNet models (299x299 instead of 224x224),
and that the input preprocessing function is also different (same as Xception).

# Reference

- [Rethinking the Inception Architecture for Computer
Vision](http://arxiv.org/abs/1512.00567)

## Functions

[`InceptionV3(...)`](../../../tf/keras/applications/InceptionV3.md): Instantiates the Inception v3 architecture.

[`decode_predictions(...)`](../../../tf/keras/applications/densenet/decode_predictions.md): Decodes the prediction of an ImageNet model.

[`preprocess_input(...)`](../../../tf/keras/applications/inception_v3/preprocess_input.md): Preprocesses a numpy array encoding a batch of images.

