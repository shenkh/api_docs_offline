<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.test.create_local_cluster" />
<meta itemprop="path" content="Stable" />
</div>

# tf.test.create_local_cluster

Create and start local servers and return the associated `Server` objects.

### Aliases:

* `tf.compat.v1.test.create_local_cluster`
* `tf.compat.v2.test.create_local_cluster`
* `tf.test.create_local_cluster`

``` python
tf.test.create_local_cluster(
    num_workers,
    num_ps,
    protocol='grpc',
    worker_config=None,
    ps_config=None
)
```



Defined in [`python/framework/test_util.py`](/code/stable/tensorflow/python/framework/test_util.py).

<!-- Placeholder for "Used in" -->

"PS" stands for "parameter server": a task responsible for storing and
updating the model's parameters. Other tasks send updates to these parameters
as they work on optimizing the parameters. This particular division of labor
between tasks is not required, but is common for distributed training.

Read more at https://www.tensorflow.org/guide/extend/architecture

![components](https://www.tensorflow.org/images/diag1.svg "components")


Figure illustrates the interaction of these components.
"/job:worker/task:0" and "/job:ps/task:0" are both tasks with worker services.


#### Example:


```python
workers, _ = tf.test.create_local_cluster(num_workers=2, num_ps=2)

worker_sessions = [tf.compat.v1.Session(w.target) for w in workers]

with tf.device("/job:ps/task:0"):
  ...
with tf.device("/job:ps/task:1"):
  ...
with tf.device("/job:worker/task:0"):
  ...
with tf.device("/job:worker/task:1"):
  ...

worker_sessions[0].run(...)
```

#### Args:


* <b>`num_workers`</b>: Number of worker servers to start.
* <b>`num_ps`</b>: Number of PS servers to start.
* <b>`protocol`</b>: Communication protocol. Allowed values are documented in the
  documentation of <a href="../../tf/distribute/Server.md"><code>tf.distribute.Server</code></a>.
* <b>`worker_config`</b>: (optional) `tf.ConfigProto` to initialize workers. Can be
  used to instantiate multiple devices etc.
* <b>`ps_config`</b>: (optional) `tf.ConfigProto` to initialize PS servers.


#### Returns:

A tuple `(worker_servers, ps_servers)`.  `worker_servers` is a list
of `num_workers` objects of type <a href="../../tf/distribute/Server.md"><code>tf.distribute.Server</code></a> (all running
locally);
and `ps_servers` is a list of `num_ps` objects of similar type.



#### Raises:


* <b>`ImportError`</b>: if portpicker module was not found at load time