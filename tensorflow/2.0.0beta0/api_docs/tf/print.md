<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.print" />
<meta itemprop="path" content="Stable" />
</div>

# tf.print

Print the specified inputs.

### Aliases:

* `tf.compat.v1.print`
* `tf.compat.v2.print`
* `tf.print`

``` python
tf.print(
    *inputs,
    **kwargs
)
```



Defined in [`python/ops/logging_ops.py`](/code/stable/tensorflow/python/ops/logging_ops.py).

<!-- Placeholder for "Used in" -->

Returns an operator that prints the specified inputs to a desired
output stream or logging level. The inputs may be dense or sparse Tensors,
primitive python objects, data structures that contain Tensors, and printable
python objects. Printed tensors will recursively show the first and last
`summarize` elements of each dimension.

With eager execution enabled and/or inside a `tf.contrib.eager.defun` this
operator will automatically execute, and users only need to call <a href="../tf/print.md"><code>tf.print</code></a>
without using the return value. When constructing graphs outside of a
`tf.contrib.eager.defun`, one must either include the returned op
in the input to `session.run`, or use the operator as a control dependency for
executed ops by specifying `with tf.control_dependencies([print_op])`.



#### Example:

Single-input usage:
```python
tf.compat.v1.enable_eager_execution()
tensor = tf.range(10)
tf.print(tensor, output_stream=sys.stderr)
```
(This prints "[0 1 2 ... 7 8 9]" to sys.stderr)

Multi-input usage:
```python
tf.compat.v1.enable_eager_execution()
tensor = tf.range(10)
tf.print("tensors:", tensor, {2: tensor * 2}, output_stream=sys.stdout)
```
(This prints "tensors: [0 1 2 ... 7 8 9] {2: [0 2 4 ... 14 16 18]}" to
sys.stdout)

Usage in a defun:
```python
tf.compat.v1.enable_eager_execution()

@tf.contrib.eager.defun
def f():
    tensor = tf.range(10)
    tf.print(tensor, output_stream=sys.stderr)
    return tensor

range_tensor = f()
```
(This prints "[0 1 2 ... 7 8 9]" to sys.stderr)

Usage when constructing graphs:
```python
sess = tf.compat.v1.Session()
with sess.as_default():
    tensor = tf.range(10)
    print_op = tf.print("tensors:", tensor, {2: tensor * 2},
                        output_stream=sys.stdout)
    with tf.control_dependencies([print_op]):
      tripled_tensor = tensor * 3
    sess.run(tripled_tensor)
```
(This prints "tensors: [0 1 2 ... 7 8 9] {2: [0 2 4 ... 14 16 18]}" to
sys.stdout)


Note: In Jupyter notebooks and colabs, this operator prints to the notebook
  cell outputs. It will not write to the notebook kernel's console logs.

#### Args:


* <b>`*inputs`</b>: Positional arguments that are the inputs to print. Inputs in the
  printed output will be separated by spaces. Inputs may be python
  primitives, tensors, data structures such as dicts and lists that may
  contain tensors (with the data structures possibly nested in arbitrary
  ways), and printable python objects.
* <b>`output_stream`</b>: The output stream, logging level, or file to print to.
  Defaults to sys.stderr, but sys.stdout, tf.compat.v1.logging.info,
  tf.compat.v1.logging.warning, and tf.compat.v1.logging.error are also
  supported. To print to
  a file, pass a string started with "file://" followed by the file path,
  e.g., "file:///tmp/foo.out".
* <b>`summarize`</b>: The first and last `summarize` elements within each dimension are
  recursively printed per Tensor. If None, then the first 3 and last 3
  elements of each dimension are printed for each tensor. If set to -1, it
  will print all elements of every tensor.
* <b>`sep`</b>: The string to use to separate the inputs. Defaults to " ".
* <b>`end`</b>: End character that is appended at the end the printed string.
  Defaults to the newline character.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A print operator that prints the specified inputs in the specified output
stream or logging level.



#### Raises:


* <b>`ValueError`</b>: If an unsupported output stream is specified.

#### Python2 Compatibility
In python 2.7, make sure to import the following:
`from __future__ import print_function`

