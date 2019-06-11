<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.SessionRunArgs" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="fetches"/>
<meta itemprop="property" content="feed_dict"/>
<meta itemprop="property" content="options"/>
</div>

# tf.estimator.SessionRunArgs

## Class `SessionRunArgs`

Represents arguments to be added to a `Session.run()` call.



### Aliases:

* Class `tf.compat.v1.estimator.SessionRunArgs`
* Class `tf.compat.v1.train.SessionRunArgs`
* Class `tf.compat.v2.estimator.SessionRunArgs`
* Class `tf.estimator.SessionRunArgs`



Defined in [`python/training/session_run_hook.py`](/code/stable/tensorflow/python/training/session_run_hook.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`fetches`</b>: Exactly like the 'fetches' argument to Session.Run().
  Can be a single tensor or op, a list of 'fetches' or a dictionary
  of fetches.  For example:
    fetches = global_step_tensor
    fetches = [train_op, summary_op, global_step_tensor]
    fetches = {'step': global_step_tensor, 'summ': summary_op}
  Note that this can recurse as expected:
    fetches = {'step': global_step_tensor,
               'ops': [train_op, check_nan_op]}
* <b>`feed_dict`</b>: Exactly like the `feed_dict` argument to `Session.Run()`
* <b>`options`</b>: Exactly like the `options` argument to `Session.run()`, i.e., a
  config_pb2.RunOptions proto.

## Properties

<h3 id="fetches"><code>fetches</code></h3>




<h3 id="feed_dict"><code>feed_dict</code></h3>




<h3 id="options"><code>options</code></h3>






