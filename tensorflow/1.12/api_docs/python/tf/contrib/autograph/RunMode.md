<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.autograph.RunMode" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="GRAPH"/>
<meta itemprop="property" content="PY_FUNC"/>
<meta itemprop="property" content="__members__"/>
</div>

# tf.contrib.autograph.RunMode

## Class `RunMode`





Defined in [`tensorflow/python/autograph/impl/api.py`](/code/stable/tensorflow/python/autograph/impl/api.py).

Specifies the way a converted function or method should be executed in TF.

The enum values have the following semantics:

 * GRAPH: Call this function directly, as-is. This is suitable for functions
     that were already designed for TF graphs and contain ops.
 * PY_FUNC: Wrap this function into a py_func op. This is suitable for code
     that will only run correctly in Python, for example code that renders
     to the display, reads keyboard input, etc.

## Class Members

<h3 id="GRAPH"><code>GRAPH</code></h3>

<h3 id="PY_FUNC"><code>PY_FUNC</code></h3>

<h3 id="__members__"><code>__members__</code></h3>

