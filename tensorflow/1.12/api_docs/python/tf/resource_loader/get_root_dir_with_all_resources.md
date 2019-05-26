<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.resource_loader.get_root_dir_with_all_resources" />
<meta itemprop="path" content="Stable" />
</div>

# tf.resource_loader.get_root_dir_with_all_resources

``` python
tf.resource_loader.get_root_dir_with_all_resources()
```



Defined in [`tensorflow/python/platform/resource_loader.py`](/code/stable/tensorflow/python/platform/resource_loader.py).

Get a root directory containing all the data attributes in the build rule.

#### Returns:

The path to the specified file present in the data attribute of py_test
or py_binary. Falls back to returning the same as get_data_files_path if it
fails to detect a bazel runfiles directory.