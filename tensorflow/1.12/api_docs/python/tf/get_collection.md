<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.get_collection" />
<meta itemprop="path" content="Stable" />
</div>

# tf.get_collection

``` python
tf.get_collection(
    key,
    scope=None
)
```



Defined in [`tensorflow/python/framework/ops.py`](/code/stable/tensorflow/python/framework/ops.py).

Wrapper for `Graph.get_collection()` using the default graph.

See <a href="../tf/Graph.md#get_collection"><code>tf.Graph.get_collection</code></a>
for more details.

#### Args:

* <b>`key`</b>: The key for the collection. For example, the `GraphKeys` class
    contains many standard names for collections.
* <b>`scope`</b>: (Optional.) If supplied, the resulting list is filtered to include
    only items whose `name` attribute matches using `re.match`. Items
    without a `name` attribute are never returned if a scope is supplied and
    the choice or `re.match` means that a `scope` without special tokens
    filters by prefix.


#### Returns:

The list of values in the collection with the given `name`, or
an empty list if no value has been added to that collection. The
list contains the values in the order under which they were
collected.



#### Eager Compatibility
Collections are not supported when eager execution is enabled.

