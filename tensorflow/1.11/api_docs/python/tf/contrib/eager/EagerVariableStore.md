<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.eager.EagerVariableStore" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="as_default"/>
<meta itemprop="property" content="copy"/>
<meta itemprop="property" content="non_trainable_variables"/>
<meta itemprop="property" content="trainable_variables"/>
<meta itemprop="property" content="variables"/>
</div>

# tf.contrib.eager.EagerVariableStore

## Class `EagerVariableStore`





Defined in [`tensorflow/python/ops/variable_scope.py`](https://www.tensorflow.org/code/tensorflow/python/ops/variable_scope.py).

Wrapper allowing functional layers to be used with eager execution.

When eager execution is enabled Variables get deleted when they go out of
scope, and are not stored in global collections by default. A lot of code
(mostly the functional layers in tf.layers) assumes that variables are kept in
a global list.

EagerVariableStore can be used in conjunction with this code to make it
eager-friendly. For example, to create a dense layer, use:

```
  container = tfe.EagerVariableStore()
  for input in dataset_iterator:
    with container.as_default():
      x = tf.layers.dense(input, name="l1")
  print(container.variables)  # Should print the variables used in the layer.
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(store=None)
```

Initialize self.  See help(type(self)) for accurate signature.



## Methods

<h3 id="as_default"><code>as_default</code></h3>

``` python
as_default()
```



<h3 id="copy"><code>copy</code></h3>

``` python
copy()
```

Copy this variable store and all of its contents.

Variables contained in this store will be copied over to the new variable
store, meaning that they can be modified without affecting the variables in
this store.

#### Returns:

A new EagerVariableStore instance containing copied variables.

<h3 id="non_trainable_variables"><code>non_trainable_variables</code></h3>

``` python
non_trainable_variables()
```



<h3 id="trainable_variables"><code>trainable_variables</code></h3>

``` python
trainable_variables()
```



<h3 id="variables"><code>variables</code></h3>

``` python
variables()
```





