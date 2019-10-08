<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.SessionRunValues" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="results"/>
<meta itemprop="property" content="options"/>
<meta itemprop="property" content="run_metadata"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.estimator.SessionRunValues

## Class `SessionRunValues`





Defined in [`tensorflow/python/training/session_run_hook.py`](/code/stable/tensorflow/python/training/session_run_hook.py).

Contains the results of `Session.run()`.

In the future we may use this object to add more information about result of
run without changing the Hook API.

#### Args:

* <b>`results`</b>: The return values from `Session.run()` corresponding to the fetches
    attribute returned in the RunArgs. Note that this has the same shape as
    the RunArgs fetches.  For example:
      fetches = global_step_tensor
      => results = nparray(int)
      fetches = [train_op, summary_op, global_step_tensor]
      => results = [None, nparray(string), nparray(int)]
      fetches = {'step': global_step_tensor, 'summ': summary_op}
      => results = {'step': nparray(int), 'summ': nparray(string)}
* <b>`options`</b>: `RunOptions` from the `Session.run()` call.
* <b>`run_metadata`</b>: `RunMetadata` from the `Session.run()` call.

<h2 id="__new__"><code>__new__</code></h2>

``` python
__new__(
    _cls,
    results,
    options,
    run_metadata
)
```

Create new instance of SessionRunValues(results, options, run_metadata)



## Properties

<h3 id="results"><code>results</code></h3>



<h3 id="options"><code>options</code></h3>



<h3 id="run_metadata"><code>run_metadata</code></h3>





