<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.autograph.set_loop_options" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.autograph.set_loop_options

``` python
tf.contrib.autograph.set_loop_options(
    parallel_iterations=UNSPECIFIED,
    back_prop=UNSPECIFIED,
    swap_memory=UNSPECIFIED,
    maximum_iterations=UNSPECIFIED
)
```



Defined in [`tensorflow/python/autograph/lang/directives.py`](/code/stable/tensorflow/python/autograph/lang/directives.py).

Specifies additional arguments to be passed to the enclosing while_loop.

The parameters apply to and only to the immediately enclosing loop. It only
has effect if the loop is staged as a TF while_loop; otherwise the parameters
have no effect.

#### Args:

* <b>`parallel_iterations`</b>: See tf.while_loop.
* <b>`back_prop`</b>: See tf.while_loop.
* <b>`swap_memory`</b>: See tf.while_loop.
* <b>`maximum_iterations`</b>: See tf.while_loop.