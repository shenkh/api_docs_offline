<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.autograph.ConversionOptions" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="recursive"/>
<meta itemprop="property" content="verbose"/>
<meta itemprop="property" content="strip_decorators"/>
<meta itemprop="property" content="force_conversion"/>
<meta itemprop="property" content="arg_types"/>
<meta itemprop="property" content="__new__"/>
<meta itemprop="property" content="new"/>
</div>

# tf.contrib.autograph.ConversionOptions

## Class `ConversionOptions`





Defined in [`tensorflow/python/autograph/impl/api.py`](/code/stable/tensorflow/python/autograph/impl/api.py).

Container for conversion flags.

#### Attributes:

* <b>`recursive`</b>: bool, whether to recursively convert any user functions or
      classes that the converted function may use.
* <b>`verbose`</b>: bool, whether to log the compiled code.
* <b>`strip_decorators`</b>: Tuple[Callable], contains decorators that should be in
      excluded from the compiled output. By default, when converting a
      function before the decorators are applied, the compiled output will
      include those decorators.
* <b>`force_conversion`</b>: bool, whether to force convertinng the target entity.
      When force_conversion is turned off, the converter may decide to
      return the function as-is.
* <b>`arg_types`</b>: Optional[Dict[Text, Type]], type hints for symbols including
      function arguments.

<h2 id="__new__"><code>__new__</code></h2>

``` python
__new__(
    _cls,
    recursive,
    verbose,
    strip_decorators,
    force_conversion,
    arg_types
)
```

Create new instance of ConversionOptions(recursive, verbose, strip_decorators, force_conversion, arg_types)



## Properties

<h3 id="recursive"><code>recursive</code></h3>



<h3 id="verbose"><code>verbose</code></h3>



<h3 id="strip_decorators"><code>strip_decorators</code></h3>



<h3 id="force_conversion"><code>force_conversion</code></h3>



<h3 id="arg_types"><code>arg_types</code></h3>





## Methods

<h3 id="new"><code>new</code></h3>

``` python
@classmethod
new(
    cls,
    recursive=False,
    verbose=False,
    strip_decorators=None,
    force_conversion=False,
    arg_types=None
)
```





