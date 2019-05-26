<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.saved_model.load" />
<meta itemprop="path" content="Stable" />
</div>

# tf.saved_model.load

### Aliases:

* `tf.saved_model.load`
* `tf.saved_model.loader.load`

``` python
tf.saved_model.load(
    sess,
    tags,
    export_dir,
    import_scope=None,
    **saver_kwargs
)
```



Defined in [`tensorflow/python/saved_model/loader_impl.py`](/code/stable/tensorflow/python/saved_model/loader_impl.py).

Loads the model from a SavedModel as specified by tags.

#### Args:

* <b>`sess`</b>: The TensorFlow session to restore the variables.
* <b>`tags`</b>: Set of string tags to identify the required MetaGraphDef. These should
      correspond to the tags used when saving the variables using the
      SavedModel `save()` API.
* <b>`export_dir`</b>: Directory in which the SavedModel protocol buffer and variables
      to be loaded are located.
* <b>`import_scope`</b>: Optional `string` -- if specified, prepend this string
      followed by '/' to all loaded tensor names. This scope is applied to
      tensor instances loaded into the passed session, but it is *not* written
      through to the static `MetaGraphDef` protocol buffer that is returned.
* <b>`**saver_kwargs`</b>: Optional keyword arguments passed through to Saver.


#### Returns:

The `MetaGraphDef` protocol buffer loaded in the provided session. This
can be used to further extract signature-defs, collection-defs, etc.


#### Raises:

* <b>`RuntimeError`</b>: MetaGraphDef associated with the tags cannot be found.