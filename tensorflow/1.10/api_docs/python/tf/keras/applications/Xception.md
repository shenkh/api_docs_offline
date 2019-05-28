<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.applications.xception" />
</div>

# Module: tf.keras.applications.xception



Defined in [`tensorflow/keras/applications/xception/__init__.py`](https://www.tensorflow.org/code/tensorflow/keras/applications/xception/__init__.py).

Xception V1 model for Keras.

On ImageNet, this model gets to a top-1 validation accuracy of 0.790
and a top-5 validation accuracy of 0.945.

Do note that the input image format for this model is different than for
the VGG16 and ResNet models (299x299 instead of 224x224),
and that the input preprocessing function
is also different (same as Inception V3).

Also do note that this model is only available for the TensorFlow backend,
due to its reliance on `SeparableConvolution` layers.

# Reference

- [Xception: Deep Learning with Depthwise Separable
Convolutions](https://arxiv.org/abs/1610.02357)

## Functions

[`Xception(...)`](../../../tf/keras/applications/Xception.md): Instantiates the Xception architecture.

[`decode_predictions(...)`](../../../tf/keras/applications/densenet/decode_predictions.md): Decodes the prediction of an ImageNet model.

[`preprocess_input(...)`](../../../tf/keras/applications/xception/preprocess_input.md): Preprocesses a numpy array encoding a batch of images.

