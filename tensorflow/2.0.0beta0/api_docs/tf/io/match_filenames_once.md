<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.match_filenames_once" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.match_filenames_once

Save the list of files matching pattern, so it is only computed once.

### Aliases:

* `tf.compat.v1.io.match_filenames_once`
* `tf.compat.v1.train.match_filenames_once`
* `tf.compat.v2.io.match_filenames_once`
* `tf.io.match_filenames_once`

``` python
tf.io.match_filenames_once(
    pattern,
    name=None
)
```



Defined in [`python/training/input.py`](/code/stable/tensorflow/python/training/input.py).

<!-- Placeholder for "Used in" -->

NOTE: The order of the files returned can be non-deterministic.

#### Args:


* <b>`pattern`</b>: A file pattern (glob), or 1D tensor of file patterns.
* <b>`name`</b>: A name for the operations (optional).


#### Returns:

A variable that is initialized to the list of files matching the pattern(s).
