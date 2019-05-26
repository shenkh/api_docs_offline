<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.Server" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="server_def"/>
<meta itemprop="property" content="target"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="create_local_server"/>
<meta itemprop="property" content="join"/>
<meta itemprop="property" content="start"/>
</div>

# tf.train.Server

## Class `Server`





Defined in [`tensorflow/python/training/server_lib.py`](https://www.tensorflow.org/code/tensorflow/python/training/server_lib.py).

An in-process TensorFlow server, for use in distributed training.

A <a href="../../tf/train/Server.md"><code>tf.train.Server</code></a> instance encapsulates a set of devices and a
<a href="../../tf/Session.md"><code>tf.Session</code></a> target that
can participate in distributed training. A server belongs to a
cluster (specified by a <a href="../../tf/train/ClusterSpec.md"><code>tf.train.ClusterSpec</code></a>), and
corresponds to a particular task in a named job. The server can
communicate with any other server in the same cluster.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    server_or_cluster_def,
    job_name=None,
    task_index=None,
    protocol=None,
    config=None,
    start=True
)
```

Creates a new server with the given definition.

The `job_name`, `task_index`, and `protocol` arguments are optional, and
override any information provided in `server_or_cluster_def`.

#### Args:

* <b>`server_or_cluster_def`</b>: A <a href="../../tf/train/ServerDef.md"><code>tf.train.ServerDef</code></a> or
    <a href="../../tf/train/ClusterDef.md"><code>tf.train.ClusterDef</code></a> protocol buffer, or a
    <a href="../../tf/train/ClusterSpec.md"><code>tf.train.ClusterSpec</code></a> object, describing the server to be
    created and/or the cluster of which it is a member.
* <b>`job_name`</b>: (Optional.) Specifies the name of the job of which the server
    is a member. Defaults to the value in `server_or_cluster_def`, if
    specified.
* <b>`task_index`</b>: (Optional.) Specifies the task index of the server in its
    job. Defaults to the value in `server_or_cluster_def`, if specified.
    Otherwise defaults to 0 if the server's job has only one task.
* <b>`protocol`</b>: (Optional.) Specifies the protocol to be used by the server.
    Acceptable values include `"grpc", "grpc+verbs"`. Defaults to the
    value in `server_or_cluster_def`, if specified. Otherwise defaults to
    `"grpc"`.
* <b>`config`</b>: (Options.) A <a href="../../tf/ConfigProto.md"><code>tf.ConfigProto</code></a> that specifies default
    configuration options for all sessions that run on this server.
* <b>`start`</b>: (Optional.) Boolean, indicating whether to start the server
    after creating it. Defaults to `True`.


#### Raises:

* <b>`tf.errors.OpError`</b>: Or one of its subclasses if an error occurs while
    creating the TensorFlow server.



## Properties

<h3 id="server_def"><code>server_def</code></h3>

Returns the <a href="../../tf/train/ServerDef.md"><code>tf.train.ServerDef</code></a> for this server.

#### Returns:

A <a href="../../tf/train/ServerDef.md"><code>tf.train.ServerDef</code></a> protocol buffer that describes the configuration
of this server.

<h3 id="target"><code>target</code></h3>

Returns the target for a <a href="../../tf/Session.md"><code>tf.Session</code></a> to connect to this server.

To create a
<a href="../../tf/Session.md"><code>tf.Session</code></a> that
connects to this server, use the following snippet:

```python
server = tf.train.Server(...)
with tf.Session(server.target):
  # ...
```

#### Returns:

A string containing a session target for this server.



## Methods

<h3 id="create_local_server"><code>create_local_server</code></h3>

``` python
@staticmethod
create_local_server(
    config=None,
    start=True
)
```

Creates a new single-process cluster running on the local host.

This method is a convenience wrapper for creating a
<a href="../../tf/train/Server.md"><code>tf.train.Server</code></a> with a <a href="../../tf/train/ServerDef.md"><code>tf.train.ServerDef</code></a> that specifies a
single-process cluster containing a single task in a job called
`"local"`.

#### Args:

* <b>`config`</b>: (Options.) A <a href="../../tf/ConfigProto.md"><code>tf.ConfigProto</code></a> that specifies default
    configuration options for all sessions that run on this server.
* <b>`start`</b>: (Optional.) Boolean, indicating whether to start the server after
    creating it. Defaults to `True`.


#### Returns:

A local <a href="../../tf/train/Server.md"><code>tf.train.Server</code></a>.

<h3 id="join"><code>join</code></h3>

``` python
join()
```

Blocks until the server has shut down.

This method currently blocks forever.

#### Raises:

* <b>`tf.errors.OpError`</b>: Or one of its subclasses if an error occurs while
    joining the TensorFlow server.

<h3 id="start"><code>start</code></h3>

``` python
start()
```

Starts this server.

#### Raises:

* <b>`tf.errors.OpError`</b>: Or one of its subclasses if an error occurs while
    starting the TensorFlow server.



