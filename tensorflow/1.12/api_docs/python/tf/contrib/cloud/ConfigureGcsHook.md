<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.cloud.ConfigureGcsHook" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="after_create_session"/>
<meta itemprop="property" content="after_run"/>
<meta itemprop="property" content="before_run"/>
<meta itemprop="property" content="begin"/>
<meta itemprop="property" content="end"/>
</div>

# tf.contrib.cloud.ConfigureGcsHook

## Class `ConfigureGcsHook`

Inherits From: [`SessionRunHook`](../../../tf/train/SessionRunHook.md)



Defined in [`tensorflow/contrib/cloud/python/ops/gcs_config_ops.py`](/code/stable/tensorflow/contrib/cloud/python/ops/gcs_config_ops.py).

ConfigureGcsHook configures GCS when used with Estimator/TPUEstimator.

Warning: GCS `credentials` may be transmitted over the network unencrypted.
Please ensure that the network is trusted before using this function. For
users running code entirely within Google Cloud, your data is protected by
encryption in between data centers. For more information, please take a look
at https://cloud.google.com/security/encryption-in-transit/.

Example:

```
sess = tf.Session()
refresh_token = raw_input("Refresh token: ")
client_secret = raw_input("Client secret: ")
client_id = "<REDACTED>"
creds = {
    "client_id": client_id,
    "refresh_token": refresh_token,
    "client_secret": client_secret,
    "type": "authorized_user",
}
tf.contrib.cloud.configure_gcs(sess, credentials=creds)
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    credentials=None,
    block_cache=None
)
```

Constructs a ConfigureGcsHook.

#### Args:

* <b>`credentials`</b>: A json-formatted string.
* <b>`block_cache`</b>: A `BlockCacheParams`


#### Raises:

* <b>`ValueError`</b>: If credentials is improperly formatted or block_cache is not a
    BlockCacheParams.



## Methods

<h3 id="after_create_session"><code>after_create_session</code></h3>

``` python
after_create_session(
    session,
    coord
)
```

Called when new TensorFlow session is created.

This is called to signal the hooks that a new session has been created. This
has two essential differences with the situation in which `begin` is called:

* When this is called, the graph is finalized and ops can no longer be added
    to the graph.
* This method will also be called as a result of recovering a wrapped
    session, not only at the beginning of the overall session.

#### Args:

* <b>`session`</b>: A TensorFlow Session that has been created.
* <b>`coord`</b>: A Coordinator object which keeps track of all threads.

<h3 id="after_run"><code>after_run</code></h3>

``` python
after_run(
    run_context,
    run_values
)
```

Called after each call to run().

The `run_values` argument contains results of requested ops/tensors by
`before_run()`.

The `run_context` argument is the same one send to `before_run` call.
`run_context.request_stop()` can be called to stop the iteration.

If `session.run()` raises any exceptions then `after_run()` is not called.

#### Args:

* <b>`run_context`</b>: A `SessionRunContext` object.
* <b>`run_values`</b>: A SessionRunValues object.

<h3 id="before_run"><code>before_run</code></h3>

``` python
before_run(run_context)
```

Called before each call to run().

You can return from this call a `SessionRunArgs` object indicating ops or
tensors to add to the upcoming `run()` call.  These ops/tensors will be run
together with the ops/tensors originally passed to the original run() call.
The run args you return can also contain feeds to be added to the run()
call.

The `run_context` argument is a `SessionRunContext` that provides
information about the upcoming `run()` call: the originally requested
op/tensors, the TensorFlow Session.

At this point graph is finalized and you can not add ops.

#### Args:

* <b>`run_context`</b>: A `SessionRunContext` object.


#### Returns:

None or a `SessionRunArgs` object.

<h3 id="begin"><code>begin</code></h3>

``` python
begin()
```

Called once before using the session.

When called, the default graph is the one that will be launched in the
session.  The hook can modify the graph by adding new operations to it.
After the `begin()` call the graph will be finalized and the other callbacks
can not modify the graph anymore. Second call of `begin()` on the same
graph, should not change the graph.

<h3 id="end"><code>end</code></h3>

``` python
end(session)
```

Called at the end of session.

The `session` argument can be used in case the hook wants to run final ops,
such as saving a last checkpoint.

If `session.run()` raises exception other than OutOfRangeError or
StopIteration then `end()` is not called.
Note the difference between `end()` and `after_run()` behavior when
`session.run()` raises OutOfRangeError or StopIteration. In that case
`end()` is called but `after_run()` is not called.

#### Args:

* <b>`session`</b>: A TensorFlow Session that will be soon closed.



