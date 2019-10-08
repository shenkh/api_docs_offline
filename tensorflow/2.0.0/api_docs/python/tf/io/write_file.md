<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.write_file" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.write_file

``` python
tf.io.write_file(
    filename,
    contents,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_io_ops.py`.

Writes contents to the file at input filename. Creates file and recursively

creates directory if not existing.

#### Args:

* <b>`filename`</b>: A `Tensor` of type `string`.
    scalar. The name of the file to which we write the contents.
* <b>`contents`</b>: A `Tensor` of type `string`.
    scalar. The content to be written to the output file.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The created Operation.