<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.MonitoredSession.StepContext" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="session"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="request_stop"/>
<meta itemprop="property" content="run_with_hooks"/>
</div>

# tf.train.MonitoredSession.StepContext

## Class `StepContext`



### Aliases:

* Class `tf.train.MonitoredSession.StepContext`
* Class `tf.train.SingularMonitoredSession.StepContext`



Defined in [`tensorflow/python/training/monitored_session.py`](https://www.tensorflow.org/code/tensorflow/python/training/monitored_session.py).

Control flow instrument for the `step_fn` from `run_step_fn()`.

Users of `step_fn` may perform `run()` calls without running hooks
by accessing the `session`.  A `run()` call with hooks may be performed
using `run_with_hooks()`.  Computation flow can be interrupted using
`request_stop()`.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    session,
    run_with_hooks_fn
)
```

Initializes the `step_context` argument for a `step_fn` invocation.

#### Args:

* <b>`session`</b>: An instance of <a href="../../../tf/Session.md"><code>tf.Session</code></a>.
* <b>`run_with_hooks_fn`</b>: A function for running fetches and hooks.



## Properties

<h3 id="session"><code>session</code></h3>





## Methods

<h3 id="request_stop"><code>request_stop</code></h3>

``` python
request_stop()
```

Exit the training loop by causing `should_stop()` to return `True`.

   Causes `step_fn` to exit by raising an exception.

#### Raises:

StopIteration

<h3 id="run_with_hooks"><code>run_with_hooks</code></h3>

``` python
run_with_hooks(
    *args,
    **kwargs
)
```

Same as `MonitoredSession.run`. Accepts the same arguments.



