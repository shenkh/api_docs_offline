<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.enable_control_flow_v2" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.enable_control_flow_v2

Use control flow v2.

``` python
tf.compat.v1.enable_control_flow_v2()
```



Defined in [`python/ops/control_flow_util.py`](/code/stable/tensorflow/python/ops/control_flow_util.py).

<!-- Placeholder for "Used in" -->

control flow v2 (cfv2) is an improved version of control flow in TensorFlow
with support for higher order derivatives. Enabling cfv2 will change the
graph/function representation of control flow, e.g., <a href="../../../tf/while_loop.md"><code>tf.while_loop</code></a> and
<a href="../../../tf/cond.md"><code>tf.cond</code></a> will generate functional `While` and `If` ops instead of low-level
`Switch`, `Merge` etc. ops. Note: Importing and running graphs exported
with old control flow will still be supported.

Calling tf.enable_control_flow_v2() lets you opt-in to this TensorFlow 2.0
feature.