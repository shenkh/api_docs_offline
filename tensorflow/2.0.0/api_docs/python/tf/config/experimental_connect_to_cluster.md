<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.experimental_connect_to_cluster" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.experimental_connect_to_cluster

``` python
tf.config.experimental_connect_to_cluster(
    cluster_spec_or_resolver,
    job_name='localhost',
    task_index=0,
    protocol=None,
    make_master_device_default=True
)
```



Defined in [`tensorflow/python/eager/remote.py`](/code/stable/tensorflow/python/eager/remote.py).

Connects to the given cluster.
Will make devices on the cluster available to use. Note that calling this more
than once will work, but will invalidate any tensor handles on the old remote
devices.
If the given local job name is not present in the cluster specification, it
will be automatically added, using an unused port on the localhost.
#### Args:

* <b>`cluster_spec_or_resolver`</b>: A `ClusterSpec` or `ClusterResolver` describing
    the cluster.
* <b>`job_name`</b>: The name of the local job.
* <b>`task_index`</b>: The local task index.
* <b>`protocol`</b>: The communication protocol, such as `"grpc"`. If unspecified, will
    use the default from `python/platform/remote_utils.py`.
* <b>`make_master_device_default`</b>: If True and a cluster resolver is passed, will
    automatically enter the master task device scope, which indicates the
    master becomes the default device to run ops. It won't do anything if
    a cluster spec is passed. Will throw an error if the caller is currently
    already in some device scope.