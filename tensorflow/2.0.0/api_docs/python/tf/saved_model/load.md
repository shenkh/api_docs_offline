<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.saved_model.load" />
<meta itemprop="path" content="Stable" />
</div>

# tf.saved_model.load

``` python
tf.saved_model.load(
    export_dir,
    tags=None
)
```



Defined in [`tensorflow/python/saved_model/load.py`](/code/stable/tensorflow/python/saved_model/load.py).

Load a SavedModel from `export_dir`.

Signatures associated with the SavedModel are available as functions:

```python
imported = tf.saved_model.load(path)
f = imported.signatures["serving_default"]
print(f(x=tf.constant([[1.]])))
```

Objects exported with <a href="../../tf/saved_model/save.md"><code>tf.saved_model.save</code></a> additionally have trackable
objects and functions assigned to attributes:

```python
exported = tf.train.Checkpoint(v=tf.Variable(3.))
exported.f = tf.function(
    lambda x: exported.v * x,
    input_signature=[tf.TensorSpec(shape=None, dtype=tf.float32)])
tf.saved_model.save(exported, path)
imported = tf.saved_model.load(path)
assert 3. == imported.v.numpy()
assert 6. == imported.f(x=tf.constant(2.)).numpy()
```

_Loading Keras models_

Keras models are trackable, so they can be saved to SavedModel. The object
returned by <a href="../../tf/saved_model/load.md"><code>tf.saved_model.load</code></a> is not a Keras object (i.e. doesn't have
`.fit`, `.predict`, etc. methods). A few attributes and functions are still
available: `.variables`, `.trainable_variables` and `.__call__`.

```python
model = tf.keras.Model(...)
tf.saved_model.save(model, path)
imported = tf.saved_model.load(path)
outputs = imported(inputs)
```

Use <a href="../../tf/keras/models/load_model.md"><code>tf.keras.models.load_model</code></a> to restore the Keras model.

_Importing SavedModels from TensorFlow 1.x_

SavedModels from <a href="../../tf/estimator/Estimator.md"><code>tf.estimator.Estimator</code></a> or 1.x SavedModel APIs have a flat
graph instead of <a href="../../tf/function.md"><code>tf.function</code></a> objects. These SavedModels will have functions
corresponding to their signatures in the `.signatures` attribute, but also
have a `.prune` method which allows you to extract functions for new
subgraphs. This is equivalent to importing the SavedModel and naming feeds and
fetches in a Session from TensorFlow 1.x.

```python
imported = tf.saved_model.load(path_to_v1_saved_model)
pruned = imported.prune("x:0", "out:0")
pruned(tf.ones([]))
```

See `tf.compat.v1.wrap_function` for details. These SavedModels also have a
`.variables` attribute containing imported variables, and a `.graph` attribute
representing the whole imported graph. For SavedModels exported from
<a href="../../tf/saved_model/save.md"><code>tf.saved_model.save</code></a>, variables are instead assigned to whichever attributes
they were assigned before export.

#### Args:

* <b>`export_dir`</b>: The SavedModel directory to load from.
* <b>`tags`</b>: A tag or sequence of tags identifying the MetaGraph to load. Optional
    if the SavedModel contains a single MetaGraph, as for those exported from
    <a href="../../tf/saved_model/load.md"><code>tf.saved_model.load</code></a>.


#### Returns:

A trackable object with a `signatures` attribute mapping from signature
keys to functions. If the SavedModel was exported by <a href="../../tf/saved_model/load.md"><code>tf.saved_model.load</code></a>,
it also points to trackable objects and functions which were attached
to the exported object.


#### Raises:

* <b>`ValueError`</b>: If `tags` don't match a MetaGraph in the SavedModel.