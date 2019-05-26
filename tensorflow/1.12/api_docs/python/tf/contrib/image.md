<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.image" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.contrib.image



Defined in [`tensorflow/contrib/image/__init__.py`](/code/stable/tensorflow/contrib/image/__init__.py).

Ops for image manipulation.

### API

This module provides functions for image manipulation; currently, chrominance
transforms (including changing saturation and hue) in YIQ space and
projective transforms (including rotation) are supported.

## Image Transformation `Ops`


## Image Segmentation `Ops`


## Matching `Ops`


## Random Dot Stereogram `Ops`


## Functions

[`angles_to_projective_transforms(...)`](../../tf/contrib/image/angles_to_projective_transforms.md): Returns projective transform(s) for the given angle(s).

[`compose_transforms(...)`](../../tf/contrib/image/compose_transforms.md): Composes the transforms tensors.

[`connected_components(...)`](../../tf/contrib/image/connected_components.md): Labels the connected components in a batch of images.

[`dense_image_warp(...)`](../../tf/contrib/image/dense_image_warp.md): Image warping using per-pixel flow vectors.

[`flat_transforms_to_matrices(...)`](../../tf/contrib/image/flat_transforms_to_matrices.md): Converts <a href="../../tf/contrib/image.md"><code>tf.contrib.image</code></a> projective transforms to affine matrices.

[`interpolate_spline(...)`](../../tf/contrib/image/interpolate_spline.md): Interpolate signal using polyharmonic interpolation.

[`matrices_to_flat_transforms(...)`](../../tf/contrib/image/matrices_to_flat_transforms.md): Converts affine matrices to <a href="../../tf/contrib/image.md"><code>tf.contrib.image</code></a> projective transforms.

[`rotate(...)`](../../tf/contrib/image/rotate.md): Rotate image(s) counterclockwise by the passed angle(s) in radians.

[`single_image_random_dot_stereograms(...)`](../../tf/contrib/image/single_image_random_dot_stereograms.md): Output a RandomDotStereogram Tensor for export via encode_PNG/JPG OP.

[`sparse_image_warp(...)`](../../tf/contrib/image/sparse_image_warp.md): Image warping using correspondences between sparse control points.

[`transform(...)`](../../tf/contrib/image/transform.md): Applies the given transform(s) to the image(s).

[`translate(...)`](../../tf/contrib/image/translate.md): Translate image(s) by the passed vectors(s).

[`translations_to_projective_transforms(...)`](../../tf/contrib/image/translations_to_projective_transforms.md): Returns projective transform(s) for the given translation(s).

