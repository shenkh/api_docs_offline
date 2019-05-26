<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.lite" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="PY3"/>
<meta itemprop="property" content="absolute_import"/>
<meta itemprop="property" content="division"/>
<meta itemprop="property" content="print_function"/>
</div>

# Module: tf.contrib.lite



Defined in [`tensorflow/contrib/lite/python/lite.py`](/code/stable/tensorflow/contrib/lite/python/lite.py).

TensorFlow Lite tooling helper functionality.

EXPERIMENTAL: APIs here are unstable and likely to change without notice.



## Modules

[`constants`](../../tf/contrib/lite/constants.md) module: Constants for TFLite.

## Classes

[`class ConverterMode`](../../tf/contrib/lite/ConverterMode.md): Enum class defining the converters available to generate TFLite models.

[`class DecodeError`](../../tf/contrib/lite/DecodeError.md): Common base class for all non-exit exceptions.

[`class Interpreter`](../../tf/contrib/lite/Interpreter.md): Interpreter inferace for TF-Lite Models.

[`class OpHint`](../../tf/contrib/lite/OpHint.md): A class that helps build tflite function invocations.

[`class TFLiteConverter`](../../tf/contrib/lite/TFLiteConverter.md): Convert a TensorFlow model into `output_format` using TOCO.

[`class TocoConverter`](../../tf/contrib/lite/TocoConverter.md): Convert a TensorFlow model into `output_format` using TOCO.

## Functions

[`build_toco_convert_protos(...)`](../../tf/contrib/lite/build_toco_convert_protos.md): Builds protocol buffers describing a conversion of a model using TOCO.

[`convert_op_hints_to_stubs(...)`](../../tf/contrib/lite/convert_op_hints_to_stubs.md): Converts a graphdef with LiteOp hints into stub operations.

[`toco_convert(...)`](../../tf/contrib/lite/toco_convert.md): Convert a model using TOCO. (deprecated)

[`toco_convert_protos(...)`](../../tf/contrib/lite/toco_convert_protos.md): Convert `input_data_str` according to model and toco parameters.

## Other Members

<h3 id="PY3"><code>PY3</code></h3>

<h3 id="absolute_import"><code>absolute_import</code></h3>

<h3 id="division"><code>division</code></h3>

<h3 id="print_function"><code>print_function</code></h3>

