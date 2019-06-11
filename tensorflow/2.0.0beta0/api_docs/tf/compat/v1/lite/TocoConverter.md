<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.lite.TocoConverter" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="from_frozen_graph"/>
<meta itemprop="property" content="from_keras_model_file"/>
<meta itemprop="property" content="from_saved_model"/>
<meta itemprop="property" content="from_session"/>
</div>

# tf.compat.v1.lite.TocoConverter

## Class `TocoConverter`

Convert a TensorFlow model into `output_format` using TOCO.





Defined in [`lite/python/lite.py`](/code/stable/tensorflow/lite/python/lite.py).

<!-- Placeholder for "Used in" -->

This class has been deprecated. Please use `lite.TFLiteConverter` instead.

## Methods

<h3 id="from_frozen_graph"><code>from_frozen_graph</code></h3>

``` python
@classmethod
from_frozen_graph(
    cls,
    graph_def_file,
    input_arrays,
    output_arrays,
    input_shapes=None
)
```

Creates a TocoConverter class from a file containing a frozen graph. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `lite.TFLiteConverter.from_frozen_graph` instead.

<h3 id="from_keras_model_file"><code>from_keras_model_file</code></h3>

``` python
@classmethod
from_keras_model_file(
    cls,
    model_file,
    input_arrays=None,
    input_shapes=None,
    output_arrays=None
)
```

Creates a TocoConverter class from a tf.keras model file. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `lite.TFLiteConverter.from_keras_model_file` instead.

<h3 id="from_saved_model"><code>from_saved_model</code></h3>

``` python
@classmethod
from_saved_model(
    cls,
    saved_model_dir,
    input_arrays=None,
    input_shapes=None,
    output_arrays=None,
    tag_set=None,
    signature_key=None
)
```

Creates a TocoConverter class from a SavedModel. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `lite.TFLiteConverter.from_saved_model` instead.

<h3 id="from_session"><code>from_session</code></h3>

``` python
@classmethod
from_session(
    cls,
    sess,
    input_tensors,
    output_tensors
)
```

Creates a TocoConverter class from a TensorFlow Session. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `lite.TFLiteConverter.from_session` instead.



