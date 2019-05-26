<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.eager.restore_variables_on_create" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.eager.restore_variables_on_create

``` python
tf.contrib.eager.restore_variables_on_create(
    *args,
    **kwds
)
```

ContextManager that restores variables on creation.

  When save_path is None (e.g. No checkpoint), does nothing.
  Otherwise, it preloads all values from checkpoint. When the
  corresponding variable is first created, it assigns the checkpoint
  value to the variable.

  ```python
  with restore_variables_on_create(
      tf.train.latest_checkpoint(checkpoint_dir)):
  ```

#### Args:

* <b>`save_path`</b>: The checkpoint file prefix.
* <b>`map_func`</b>: A function that given the variable name as argument
      and returns a variable name in checkpoint for restore. If
      None, use the variable with the same name in checkpoint to restore.
      It's an error that the mapped variable name doesn't exist in
      checkpoint.


#### Yields:

Nothing.


#### Raises:

* <b>`NotFoundError`</b>: If the variable is not found in checkpoint.
* <b>`ValueError`</b>: If not used in eager mode or map_func is not callable.