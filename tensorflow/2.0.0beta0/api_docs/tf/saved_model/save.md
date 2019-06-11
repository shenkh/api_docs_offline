<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.saved_model.save" />
<meta itemprop="path" content="Stable" />
</div>

# tf.saved_model.save

Exports the Trackable object `obj` to [SavedModel format](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/saved_model/README.md).

### Aliases:

* `tf.compat.v1.saved_model.experimental.save`
* `tf.compat.v1.saved_model.save`
* `tf.compat.v2.saved_model.save`
* `tf.saved_model.save`

``` python
tf.saved_model.save(
    obj,
    export_dir,
    signatures=None
)
```



Defined in [`python/saved_model/save.py`](/code/stable/tensorflow/python/saved_model/save.py).

<!-- Placeholder for "Used in" -->


#### Example usage:



```python
class Adder(tf.Module):

  @tf.function(input_signature=[tf.TensorSpec(shape=None, dtype=tf.float32)])
  def add(self, x):
    return x + x + 1.

to_export = Adder()
tf.saved_model.save(to_export, '/tmp/adder')
```

The resulting SavedModel is then servable with an input named "x", its value
having any shape and dtype float32.

The optional `signatures` argument controls which methods in `obj` will be
available to programs which consume `SavedModel`s, for example serving
APIs. Python functions may be decorated with
`@tf.function(input_signature=...)` and passed as signatures directly, or
lazily with a call to `get_concrete_function` on the method decorated with
`@tf.function`.

If the `signatures` argument is omitted, `obj` will be searched for
`@tf.function`-decorated methods. If exactly one `@tf.function` is found, that
method will be used as the default signature for the SavedModel. This behavior
is expected to change in the future, when a corresponding
<a href="../../tf/saved_model/load.md"><code>tf.saved_model.load</code></a> symbol is added. At that point signatures will be
completely optional, and any `@tf.function` attached to `obj` or its
dependencies will be exported for use with `load`.

When invoking a signature in an exported SavedModel, `Tensor` arguments are
identified by name. These names will come from the Python function's argument
names by default. They may be overridden by specifying a `name=...` argument
in the corresponding <a href="../../tf/TensorSpec.md"><code>tf.TensorSpec</code></a> object. Explicit naming is required if
multiple `Tensor`s are passed through a single argument to the Python
function.

The outputs of functions used as `signatures` must either be flat lists, in
which case outputs will be numbered, or a dictionary mapping string keys to
`Tensor`, in which case the keys will be used to name outputs.

Signatures are available in objects returned by <a href="../../tf/saved_model/load.md"><code>tf.saved_model.load</code></a> as a
`.signatures` attribute. This is a reserved attribute: <a href="../../tf/saved_model/save.md"><code>tf.saved_model.save</code></a>
on an object with a custom `.signatures` attribute will raise an exception.

Since <a href="../../tf/keras/Model.md"><code>tf.keras.Model</code></a> objects are also Trackable, this function can be
used to export Keras models. For example, exporting with a signature
specified:

```python
class Model(tf.keras.Model):

  @tf.function(input_signature=[tf.TensorSpec(shape=[None], dtype=tf.string)])
  def serve(self, serialized):
    ...

m = Model()
tf.saved_model.save(m, '/tmp/saved_model/')
```

Exporting from a function without a fixed signature:

```python
class Model(tf.keras.Model):

  @tf.function
  def call(self, x):
    ...

m = Model()
tf.saved_model.save(
    m, '/tmp/saved_model/',
    signatures=m.call.get_concrete_function(
        tf.TensorSpec(shape=[None, 3], dtype=tf.float32, name="inp")))
```

<a href="../../tf/keras/Model.md"><code>tf.keras.Model</code></a> instances constructed from inputs and outputs already have a
signature and so do not require a `@tf.function` decorator or a `signatures`
argument. If neither are specified, the model's forward pass is exported.

```python
x = input_layer.Input((4,), name="x")
y = core.Dense(5, name="out")(x)
model = training.Model(x, y)
tf.saved_model.save(model, '/tmp/saved_model/')
# The exported SavedModel takes "x" with shape [None, 4] and returns "out"
# with shape [None, 5]
```

Variables must be tracked by assigning them to an attribute of a tracked
object or to an attribute of `obj` directly. TensorFlow objects (e.g. layers
from <a href="../../tf/keras/layers.md"><code>tf.keras.layers</code></a>, optimizers from <a href="../../tf/train.md"><code>tf.train</code></a>) track their variables
automatically. This is the same tracking scheme that <a href="../../tf/train/Checkpoint.md"><code>tf.train.Checkpoint</code></a>
uses, and an exported `Checkpoint` object may be restored as a training
checkpoint by pointing <a href="../../tf/train/Checkpoint.md#restore"><code>tf.train.Checkpoint.restore</code></a> to the SavedModel's
"variables/" subdirectory. Currently variables are the only stateful objects
supported by <a href="../../tf/saved_model/save.md"><code>tf.saved_model.save</code></a>, but others (e.g. tables) will be supported
in the future.

<a href="../../tf/function.md"><code>tf.function</code></a> does not hard-code device annotations from outside the function
body, instead using the calling context's device. This means for example that
exporting a model which runs on a GPU and serving it on a CPU will generally
work, with some exceptions. <a href="../../tf/device.md"><code>tf.device</code></a> annotations inside the body of the
function will be hard-coded in the exported model; this type of annotation is
discouraged. Device-specific operations, e.g. with "cuDNN" in the name or with
device-specific layouts, may cause issues. Currently a `DistributionStrategy`
is another exception: active distribution strategies will cause device
placements to be hard-coded in a function. Exporting a single-device
computation and importing under a `DistributionStrategy` is not currently
supported, but may be in the future.

SavedModels exported with <a href="../../tf/saved_model/save.md"><code>tf.saved_model.save</code></a> [strip default-valued
attributes](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/saved_model/README.md#stripping-default-valued-attributes)
automatically, which removes one source of incompatibilities when the consumer
of a SavedModel is running an older TensorFlow version than the
producer. There are however other sources of incompatibilities which are not
handled automatically, such as when the exported model contains operations
which the consumer does not have definitions for.

#### Args:


* <b>`obj`</b>: A trackable object to export.
* <b>`export_dir`</b>: A directory in which to write the SavedModel.
* <b>`signatures`</b>: Optional, either a <a href="../../tf/function.md"><code>tf.function</code></a> with an input signature
  specified or the result of `f.get_concrete_function` on a
  `@tf.function`-decorated function `f`, in which case `f` will be used to
  generate a signature for the SavedModel under the default serving
  signature key. `signatures` may also be a dictionary, in which case it
  maps from signature keys to either <a href="../../tf/function.md"><code>tf.function</code></a> instances with input
  signatures or concrete functions. The keys of such a dictionary may be
  arbitrary strings, but will typically be from the
  `tf.saved_model.signature_constants` module.


#### Raises:


* <b>`ValueError`</b>: If `obj` is not trackable.



#### Eager Compatibility
Not well supported when graph building. From TensorFlow 1.x,
`tf.compat.v1.enable_eager_execution()` should run first. Calling
tf.saved_model.save in a loop when graph building from TensorFlow 1.x will
add new save operations to the default graph each iteration.

May not be called from within a function body.

