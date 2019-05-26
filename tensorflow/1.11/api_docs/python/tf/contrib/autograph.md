<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.autograph" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.contrib.autograph



Defined in [`tensorflow/contrib/autograph/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/autograph/__init__.py).

Autograph compiles Python code into equivalent TensorFlow code.

Equivalent here means that they have the same effect when executed.

## Classes

[`class AutographParseError`](../../tf/contrib/autograph/AutographParseError.md): Invalid syntax.

[`class GraphConstructionError`](../../tf/contrib/autograph/GraphConstructionError.md): Error for graph construction errors from AutoGraph generated code.

[`class RunMode`](../../tf/contrib/autograph/RunMode.md): Specifies the way a converted function or method should be executed in TF.

[`class TfRuntimeError`](../../tf/contrib/autograph/TfRuntimeError.md): Error wrapper for runtime errors raised by AutoGraph generated code.

## Functions

[`convert(...)`](../../tf/contrib/autograph/convert.md): Decorator that compiles a function to use TensorFlow ops.

[`converted_call(...)`](../../tf/contrib/autograph/converted_call.md): Compiles a function call inline. For internal use only.

[`do_not_convert(...)`](../../tf/contrib/autograph/do_not_convert.md): Decorator that suppresses the conversion of a function.

[`improved_errors(...)`](../../tf/contrib/autograph/improved_errors.md): Context manager that rewrites runtime errors.

[`set_element_type(...)`](../../tf/contrib/autograph/set_element_type.md): Indicates that the entity is expected hold items of specified type/shape.

[`set_loop_options(...)`](../../tf/contrib/autograph/set_loop_options.md): Specifies additional arguments to be passed to the enclosing while_loop.

[`stack(...)`](../../tf/contrib/autograph/stack.md): Stacks the input, if it admits the notion of stacking.

[`tensor_list(...)`](../../tf/contrib/autograph/tensor_list.md): Creates an tensor list and populates it with the given elements.

[`to_code(...)`](../../tf/contrib/autograph/to_code.md): Returns the equivalent code that uses TensorFlow ops.

[`to_graph(...)`](../../tf/contrib/autograph/to_graph.md): Converts a Python entity into equivalent code that uses TensorFlow ops.

