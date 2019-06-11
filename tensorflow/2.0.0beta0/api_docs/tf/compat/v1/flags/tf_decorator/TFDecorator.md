<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.tf_decorator.TFDecorator" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="decorated_target"/>
<meta itemprop="property" content="decorator_argspec"/>
<meta itemprop="property" content="decorator_doc"/>
<meta itemprop="property" content="decorator_name"/>
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.compat.v1.flags.tf_decorator.TFDecorator

## Class `TFDecorator`

Base class for all TensorFlow decorators.



### Aliases:

* Class `tf.compat.v1.app.flags.tf_decorator.TFDecorator`
* Class `tf.compat.v1.flags.tf_decorator.TFDecorator`



Defined in [`python/util/tf_decorator.py`](/code/stable/tensorflow/python/util/tf_decorator.py).

<!-- Placeholder for "Used in" -->

TFDecorator captures and exposes the wrapped target, and provides details
about the current decorator.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    decorator_name,
    target,
    decorator_doc='',
    decorator_argspec=None
)
```

Initialize self.  See help(type(self)) for accurate signature.




## Properties

<h3 id="decorated_target"><code>decorated_target</code></h3>




<h3 id="decorator_argspec"><code>decorator_argspec</code></h3>




<h3 id="decorator_doc"><code>decorator_doc</code></h3>




<h3 id="decorator_name"><code>decorator_name</code></h3>






## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    *args,
    **kwargs
)
```

Call self as a function.




