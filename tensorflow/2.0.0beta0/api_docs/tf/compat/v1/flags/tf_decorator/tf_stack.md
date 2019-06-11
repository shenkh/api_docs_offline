<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.tf_decorator.tf_stack" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="TB_CODEDICT"/>
<meta itemprop="property" content="TB_FILENAME"/>
<meta itemprop="property" content="TB_FUNCNAME"/>
<meta itemprop="property" content="TB_LINENO"/>
<meta itemprop="property" content="stacks"/>
</div>

# Module: tf.compat.v1.flags.tf_decorator.tf_stack

Functions used to extract and analyze stacks.  Faster than Python libs.

### Aliases:

* Module `tf.compat.v1.app.flags.tf_decorator.tf_stack`
* Module `tf.compat.v1.flags.tf_decorator.tf_stack`



Defined in [`python/util/tf_stack.py`](/code/stable/tensorflow/python/util/tf_stack.py).

<!-- Placeholder for "Used in" -->


## Classes

[`class CurrentModuleFilter`](../../../../../tf/compat/v1/flags/tf_decorator/tf_stack/CurrentModuleFilter.md): Filters stack frames from the module where this is used (best effort).

[`class FileAndLine`](../../../../../tf/compat/v1/flags/tf_decorator/tf_stack/FileAndLine.md): FileAndLine(file, line)

[`class StackTraceFilter`](../../../../../tf/compat/v1/flags/tf_decorator/tf_stack/StackTraceFilter.md): Allows filtering traceback information by removing superfluous frames.

[`class StackTraceMapper`](../../../../../tf/compat/v1/flags/tf_decorator/tf_stack/StackTraceMapper.md): Allows remapping traceback information to different source code.

## Functions

[`convert_stack(...)`](../../../../../tf/compat/v1/flags/tf_decorator/tf_stack/convert_stack.md): Converts a stack extracted using extract_stack() to a traceback stack.

[`extract_stack(...)`](../../../../../tf/compat/v1/flags/tf_decorator/tf_stack/extract_stack.md): A lightweight, extensible re-implementation of traceback.extract_stack.

[`extract_stack_file_and_line(...)`](../../../../../tf/compat/v1/flags/tf_decorator/tf_stack/extract_stack_file_and_line.md): A version of extract_stack that only returns filenames and line numbers.

## Other Members

* `TB_CODEDICT = 3` <a id="TB_CODEDICT"></a>
* `TB_FILENAME = 0` <a id="TB_FILENAME"></a>
* `TB_FUNCNAME = 2` <a id="TB_FUNCNAME"></a>
* `TB_LINENO = 1` <a id="TB_LINENO"></a>
* `stacks` <a id="stacks"></a>
