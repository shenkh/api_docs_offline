# Tensor Transformations

Note: Functions taking `Tensor` arguments can also take anything accepted by
<a href="../../api_docs/python/tf/convert_to_tensor.md"><code>tf.convert_to_tensor</code></a>.

[TOC]

<h2 id="Casting">Casting</h2>

TensorFlow provides several operations that you can use to cast tensor data
types in your graph.

*   <a href="../../api_docs/python/tf/string_to_number.md"><code>tf.string_to_number</code></a>
*   <a href="../../api_docs/python/tf/to_double.md"><code>tf.to_double</code></a>
*   <a href="../../api_docs/python/tf/to_float.md"><code>tf.to_float</code></a>
*   <a href="../../api_docs/python/tf/to_bfloat16.md"><code>tf.to_bfloat16</code></a>
*   <a href="../../api_docs/python/tf/to_int32.md"><code>tf.to_int32</code></a>
*   <a href="../../api_docs/python/tf/to_int64.md"><code>tf.to_int64</code></a>
*   <a href="../../api_docs/python/tf/cast.md"><code>tf.cast</code></a>
*   <a href="../../api_docs/python/tf/bitcast.md"><code>tf.bitcast</code></a>
*   <a href="../../api_docs/python/tf/saturate_cast.md"><code>tf.saturate_cast</code></a>

<h2 id="Shapes_and_Shaping">Shapes and Shaping</h2>

TensorFlow provides several operations that you can use to determine the shape
of a tensor and change the shape of a tensor.

*   <a href="../../api_docs/python/tf/broadcast_dynamic_shape.md"><code>tf.broadcast_dynamic_shape</code></a>
*   <a href="../../api_docs/python/tf/broadcast_static_shape.md"><code>tf.broadcast_static_shape</code></a>
*   <a href="../../api_docs/python/tf/shape.md"><code>tf.shape</code></a>
*   <a href="../../api_docs/python/tf/shape_n.md"><code>tf.shape_n</code></a>
*   <a href="../../api_docs/python/tf/size.md"><code>tf.size</code></a>
*   <a href="../../api_docs/python/tf/rank.md"><code>tf.rank</code></a>
*   <a href="../../api_docs/python/tf/reshape.md"><code>tf.reshape</code></a>
*   <a href="../../api_docs/python/tf/squeeze.md"><code>tf.squeeze</code></a>
*   <a href="../../api_docs/python/tf/expand_dims.md"><code>tf.expand_dims</code></a>
*   <a href="../../api_docs/python/tf/meshgrid.md"><code>tf.meshgrid</code></a>

<h2 id="Slicing_and_Joining">Slicing and Joining</h2>

TensorFlow provides several operations to slice or extract parts of a tensor,
or join multiple tensors together.

*   <a href="../../api_docs/python/tf/slice.md"><code>tf.slice</code></a>
*   <a href="../../api_docs/python/tf/strided_slice.md"><code>tf.strided_slice</code></a>
*   <a href="../../api_docs/python/tf/split.md"><code>tf.split</code></a>
*   <a href="../../api_docs/python/tf/tile.md"><code>tf.tile</code></a>
*   <a href="../../api_docs/python/tf/pad.md"><code>tf.pad</code></a>
*   <a href="../../api_docs/python/tf/concat.md"><code>tf.concat</code></a>
*   <a href="../../api_docs/python/tf/stack.md"><code>tf.stack</code></a>
*   <a href="../../api_docs/python/tf/parallel_stack.md"><code>tf.parallel_stack</code></a>
*   <a href="../../api_docs/python/tf/unstack.md"><code>tf.unstack</code></a>
*   <a href="../../api_docs/python/tf/reverse_sequence.md"><code>tf.reverse_sequence</code></a>
*   <a href="../../api_docs/python/tf/reverse.md"><code>tf.reverse</code></a>
*   <a href="../../api_docs/python/tf/reverse.md"><code>tf.reverse_v2</code></a>
*   <a href="../../api_docs/python/tf/transpose.md"><code>tf.transpose</code></a>
*   <a href="../../api_docs/python/tf/extract_image_patches.md"><code>tf.extract_image_patches</code></a>
*   <a href="../../api_docs/python/tf/space_to_batch_nd.md"><code>tf.space_to_batch_nd</code></a>
*   <a href="../../api_docs/python/tf/space_to_batch.md"><code>tf.space_to_batch</code></a>
*   <a href="../../api_docs/python/tf/required_space_to_batch_paddings.md"><code>tf.required_space_to_batch_paddings</code></a>
*   <a href="../../api_docs/python/tf/batch_to_space_nd.md"><code>tf.batch_to_space_nd</code></a>
*   <a href="../../api_docs/python/tf/batch_to_space.md"><code>tf.batch_to_space</code></a>
*   <a href="../../api_docs/python/tf/space_to_depth.md"><code>tf.space_to_depth</code></a>
*   <a href="../../api_docs/python/tf/depth_to_space.md"><code>tf.depth_to_space</code></a>
*   <a href="../../api_docs/python/tf/gather.md"><code>tf.gather</code></a>
*   <a href="../../api_docs/python/tf/gather_nd.md"><code>tf.gather_nd</code></a>
*   <a href="../../api_docs/python/tf/unique_with_counts.md"><code>tf.unique_with_counts</code></a>
*   <a href="../../api_docs/python/tf/scatter_nd.md"><code>tf.scatter_nd</code></a>
*   <a href="../../api_docs/python/tf/dynamic_partition.md"><code>tf.dynamic_partition</code></a>
*   <a href="../../api_docs/python/tf/dynamic_stitch.md"><code>tf.dynamic_stitch</code></a>
*   <a href="../../api_docs/python/tf/boolean_mask.md"><code>tf.boolean_mask</code></a>
*   <a href="../../api_docs/python/tf/one_hot.md"><code>tf.one_hot</code></a>
*   <a href="../../api_docs/python/tf/sequence_mask.md"><code>tf.sequence_mask</code></a>
*   <a href="../../api_docs/python/tf/dequantize.md"><code>tf.dequantize</code></a>
*   <a href="../../api_docs/python/tf/quantize_v2.md"><code>tf.quantize_v2</code></a>
*   <a href="../../api_docs/python/tf/quantized_concat.md"><code>tf.quantized_concat</code></a>
*   <a href="../../api_docs/python/tf/setdiff1d.md"><code>tf.setdiff1d</code></a>

<h2 id="Fake_quantization">Fake quantization</h2>
Operations used to help train for better quantization accuracy.

*   <a href="../../api_docs/python/tf/fake_quant_with_min_max_args.md"><code>tf.fake_quant_with_min_max_args</code></a>
*   <a href="../../api_docs/python/tf/fake_quant_with_min_max_args_gradient.md"><code>tf.fake_quant_with_min_max_args_gradient</code></a>
*   <a href="../../api_docs/python/tf/fake_quant_with_min_max_vars.md"><code>tf.fake_quant_with_min_max_vars</code></a>
*   <a href="../../api_docs/python/tf/fake_quant_with_min_max_vars_gradient.md"><code>tf.fake_quant_with_min_max_vars_gradient</code></a>
*   <a href="../../api_docs/python/tf/fake_quant_with_min_max_vars_per_channel.md"><code>tf.fake_quant_with_min_max_vars_per_channel</code></a>
*   <a href="../../api_docs/python/tf/fake_quant_with_min_max_vars_per_channel_gradient.md"><code>tf.fake_quant_with_min_max_vars_per_channel_gradient</code></a>
