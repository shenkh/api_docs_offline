<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.SessionRunValues" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="results"/>
<meta itemprop="property" content="options"/>
<meta itemprop="property" content="run_metadata"/>
</div>

# tf.estimator.SessionRunValues

## Class `SessionRunValues`

Contains the results of `Session.run()`.



### Aliases:

* Class `tf.compat.v1.estimator.SessionRunValues`
* Class `tf.compat.v1.train.SessionRunValues`
* Class `tf.compat.v2.estimator.SessionRunValues`
* Class `tf.estimator.SessionRunValues`



Defined in [`python/training/session_run_hook.py`](/code/stable/tensorflow/python/training/session_run_hook.py).

<!-- Placeholder for "Used in" -->

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

## Properties

<h3 id="results"><code>results</code></h3>




<h3 id="options"><code>options</code></h3>




<h3 id="run_metadata"><code>run_metadata</code></h3>






