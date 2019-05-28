<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.checkpoint.Mapping" />
<meta itemprop="property" content="layers"/>
<meta itemprop="property" content="losses"/>
<meta itemprop="property" content="non_trainable_variables"/>
<meta itemprop="property" content="non_trainable_weights"/>
<meta itemprop="property" content="trainable_variables"/>
<meta itemprop="property" content="trainable_weights"/>
<meta itemprop="property" content="updates"/>
<meta itemprop="property" content="variables"/>
<meta itemprop="property" content="weights"/>
<meta itemprop="property" content="__contains__"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__getitem__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__iter__"/>
<meta itemprop="property" content="__len__"/>
<meta itemprop="property" content="__setitem__"/>
<meta itemprop="property" content="__subclasshook__"/>
<meta itemprop="property" content="get"/>
<meta itemprop="property" content="items"/>
<meta itemprop="property" content="keys"/>
<meta itemprop="property" content="update"/>
<meta itemprop="property" content="values"/>
<meta itemprop="property" content="__reversed__"/>
</div>

# tf.contrib.checkpoint.Mapping

## Class `Mapping`





Defined in [`tensorflow/python/training/checkpointable/data_structures.py`](https://www.tensorflow.org/code/tensorflow/python/training/checkpointable/data_structures.py).

An append-only checkpointable mapping data structure with string keys.

Maintains checkpoint dependencies on its contents (which must also be
checkpointable), named based on its keys.

Note that once a key has been added, it may not be deleted or replaced. If
names may not be unique, see <a href="../../../tf/contrib/checkpoint/UniqueNameTracker.md"><code>tf.contrib.checkpoint.UniqueNameTracker</code></a>.

## Properties

<h3 id="layers"><code>layers</code></h3>



<h3 id="losses"><code>losses</code></h3>

Aggregate losses from any `Layer` instances.

<h3 id="non_trainable_variables"><code>non_trainable_variables</code></h3>



<h3 id="non_trainable_weights"><code>non_trainable_weights</code></h3>



<h3 id="trainable_variables"><code>trainable_variables</code></h3>



<h3 id="trainable_weights"><code>trainable_weights</code></h3>



<h3 id="updates"><code>updates</code></h3>

Aggregate updates from any `Layer` instances.

<h3 id="variables"><code>variables</code></h3>



<h3 id="weights"><code>weights</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    *args,
    **kwargs
)
```

Construct a new sequence. Arguments are passed to `dict()`.

<h3 id="__contains__"><code>__contains__</code></h3>

``` python
__contains__(key)
```



<h3 id="__eq__"><code>__eq__</code></h3>

``` python
__eq__(other)
```

Return self==value.

<h3 id="__getitem__"><code>__getitem__</code></h3>

``` python
__getitem__(key)
```



<h3 id="__iter__"><code>__iter__</code></h3>

``` python
__iter__()
```



<h3 id="__len__"><code>__len__</code></h3>

``` python
__len__()
```



<h3 id="__setitem__"><code>__setitem__</code></h3>

``` python
__setitem__(
    key,
    value
)
```



<h3 id="__subclasshook__"><code>__subclasshook__</code></h3>

``` python
__subclasshook__(
    cls,
    C
)
```

Abstract classes can override this to customize issubclass().

This is invoked early on by abc.ABCMeta.__subclasscheck__().
It should return True, False or NotImplemented.  If it returns
NotImplemented, the normal algorithm is used.  Otherwise, it
overrides the normal algorithm (and the outcome is cached).

<h3 id="get"><code>get</code></h3>

``` python
get(
    key,
    default=None
)
```

D.get(k[,d]) -> D[k] if k in D, else d.  d defaults to None.

<h3 id="items"><code>items</code></h3>

``` python
items()
```

D.items() -> a set-like object providing a view on D's items

<h3 id="keys"><code>keys</code></h3>

``` python
keys()
```

D.keys() -> a set-like object providing a view on D's keys

<h3 id="update"><code>update</code></h3>

``` python
update(
    *args,
    **kwargs
)
```



<h3 id="values"><code>values</code></h3>

``` python
values()
```

D.values() -> an object providing a view on D's values



## Class Members

<h3 id="__reversed__"><code>__reversed__</code></h3>

