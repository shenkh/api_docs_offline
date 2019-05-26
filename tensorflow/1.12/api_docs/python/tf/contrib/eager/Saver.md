<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.eager.Saver" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="restore"/>
<meta itemprop="property" content="save"/>
</div>

# tf.contrib.eager.Saver

## Class `Saver`





Defined in [`tensorflow/contrib/eager/python/saver.py`](/code/stable/tensorflow/contrib/eager/python/saver.py).

A tf.train.Saver adapter for use when eager execution is enabled.
  

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(var_list)
```

A  tf.train.Saver adapter for use when eager execution is enabled.

  The API, and on-disk format, mimic tf.train.Saver except that no
  Session is needed.

#### Args:

* <b>`var_list`</b>: The list of variables that will be saved and restored. Either a
    list of <a href="../../../tf/Variable.md"><code>tf.Variable</code></a> objects, or a dictionary mapping names to
    <a href="../../../tf/Variable.md"><code>tf.Variable</code></a> objects.


#### Raises:

* <b>`RuntimeError`</b>: if invoked when eager execution has not been enabled.



## Methods

<h3 id="restore"><code>restore</code></h3>

``` python
restore(file_prefix)
```

Restores previously saved variables.

#### Args:

* <b>`file_prefix`</b>: Path prefix where parameters were previously saved.
    Typically obtained from a previous `save()` call, or from
    <a href="../../../tf/train/latest_checkpoint.md"><code>tf.train.latest_checkpoint</code></a>.

<h3 id="save"><code>save</code></h3>

``` python
save(
    file_prefix,
    global_step=None
)
```

Saves variables.

#### Args:

* <b>`file_prefix`</b>: Path prefix of files created for the checkpoint.
* <b>`global_step`</b>: If provided the global step number is appended to file_prefix
    to create the checkpoint filename. The optional argument can be a
    Tensor, a Variable, or an integer.


#### Returns:

A string: prefix of filenames created for the checkpoint. This may be
 an extension of file_prefix that is suitable to pass as an argument
 to a subsequent call to `restore()`.



