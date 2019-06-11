<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.train.ChiefSessionCreator" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="create_session"/>
</div>

# tf.compat.v1.train.ChiefSessionCreator

## Class `ChiefSessionCreator`

Creates a tf.compat.v1.Session for a chief.

Inherits From: [`SessionCreator`](../../../../tf/compat/v1/train/SessionCreator.md)



Defined in [`python/training/monitored_session.py`](/code/stable/tensorflow/python/training/monitored_session.py).

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    scaffold=None,
    master='',
    config=None,
    checkpoint_dir=None,
    checkpoint_filename_with_path=None
)
```

Initializes a chief session creator.


#### Args:


* <b>`scaffold`</b>: A `Scaffold` used for gathering or building supportive ops. If
  not specified a default one is created. It's used to finalize the graph.
* <b>`master`</b>: `String` representation of the TensorFlow master to use.
* <b>`config`</b>: `ConfigProto` proto used to configure the session.
* <b>`checkpoint_dir`</b>: A string.  Optional path to a directory where to restore
  variables.
* <b>`checkpoint_filename_with_path`</b>: Full file name path to the checkpoint file.



## Methods

<h3 id="create_session"><code>create_session</code></h3>

``` python
create_session()
```






