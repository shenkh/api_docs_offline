<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.image" />
</div>

# Module: tf.keras.preprocessing.image



Defined in [`tensorflow/keras/preprocessing/image/__init__.py`](https://www.tensorflow.org/code/tensorflow/keras/preprocessing/image/__init__.py).

Fairly basic set of tools for real-time data augmentation on image data.

Can easily be extended to include new transformations,
new preprocessing methods, etc...

## Classes

[`class DirectoryIterator`](../../../tf/keras/preprocessing/image/DirectoryIterator.md): Iterator capable of reading images from a directory on disk.

[`class ImageDataGenerator`](../../../tf/keras/preprocessing/image/ImageDataGenerator.md): Generates batches of tensor image data with real-time data augmentation.

[`class Iterator`](../../../tf/keras/preprocessing/image/Iterator.md): Base class for image data iterators.

[`class NumpyArrayIterator`](../../../tf/keras/preprocessing/image/NumpyArrayIterator.md): Iterator yielding data from a Numpy array.

## Functions

[`apply_transform(...)`](../../../tf/keras/preprocessing/image/apply_transform.md): Apply the image transformation specified by a matrix.

[`array_to_img(...)`](../../../tf/keras/preprocessing/image/array_to_img.md): Converts a 3D Numpy array to a PIL Image instance.

[`flip_axis(...)`](../../../tf/keras/preprocessing/image/flip_axis.md)

[`img_to_array(...)`](../../../tf/keras/preprocessing/image/img_to_array.md): Converts a PIL Image instance to a Numpy array.

[`load_img(...)`](../../../tf/keras/preprocessing/image/load_img.md): Loads an image into PIL format.

[`random_brightness(...)`](../../../tf/keras/preprocessing/image/random_brightness.md): Performs a random adjustment of brightness of a Numpy image tensor.

[`random_channel_shift(...)`](../../../tf/keras/preprocessing/image/random_channel_shift.md): Perform a random channel shift.

[`random_rotation(...)`](../../../tf/keras/preprocessing/image/random_rotation.md): Performs a random rotation of a Numpy image tensor.

[`random_shear(...)`](../../../tf/keras/preprocessing/image/random_shear.md): Performs a random spatial shear of a Numpy image tensor.

[`random_shift(...)`](../../../tf/keras/preprocessing/image/random_shift.md): Performs a random spatial shift of a Numpy image tensor.

[`random_zoom(...)`](../../../tf/keras/preprocessing/image/random_zoom.md): Performs a random spatial zoom of a Numpy image tensor.

