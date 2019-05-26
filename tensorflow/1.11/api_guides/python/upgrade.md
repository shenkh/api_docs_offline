# Upgrade to TensorFlow 1.0

The APIs in TensorFlow 1.0 have changed in ways that are not all backwards
compatible.  That is, TensorFlow programs that worked on TensorFlow 0.n won't
necessarily work on TensorFlow 1.0.  We have made this API changes to ensure an
internally-consistent API, and do not plan to make backwards-breaking changes
throughout the 1.N lifecycle.

This guide walks you through the major changes in the API and how to
automatically upgrade your programs for TensorFlow 1.0.  This guide not
only steps you through the changes but also explains why we've made them.

<h2 id="How_to_upgrade">How to upgrade</h2>

If you would like to automatically  port your code to 1.0, you can try our
`tf_upgrade.py` script. While this script handles many cases, manual changes
are sometimes necessary.
  Get this script from our
[GitHub tree](https://github.com/tensorflow/tensorflow/tree/master/tensorflow/tools/compatibility).

To convert a single 0.n TensorFlow source file to 1.0, enter a
command of the following format:

<pre>
$ <b>python tf_upgrade.py --infile</b> <i>InputFile</i> <b>--outfile</b> <i>OutputFile</i>
</pre>

For example, the following command converts a 0.n TensorFlow
program named `test.py` to a 1.0 TensorFlow program named `test_1.0.py`:

<pre>
$ <b>python tf_upgrade.py --infile test.py --outfile test_1.0.py</b>
</pre>

The `tf_upgrade.py` script also generates a file named `report.txt`, which
details all the changes it performed and makes additional suggestions about
changes you might need to make manually.

To upgrade a whole directory of 0.n TensorFlow programs to 1.0,
enter a command having the following format:

<pre>
$ <b>python tf_upgrade.py --intree</b> <i>InputDir</i> <b>--outtree</b> <i>OutputDir</i>
</pre>

For example, the following command converts all the 0.n TensorFlow programs
in the `/home/user/cool` directory, creating their 1.0 equivalents in
the `/home/user/cool_1.0` directory:

<pre>
$ <b>python tf_upgrade.py --intree /home/user/cool --outtree /home/user/cool_1.0</b>
</pre>

### Limitations

There are a few things to watch out for. Specifically:

 * You must manually fix any instances of `tf.reverse()`.
   The `tf_upgrade.py` script will warn you about `tf.reverse()` in
   stdout and in the `report.txt` file.
 * On reordered arguments, `tf_upgrade.py` tries to minimally reformat
   your code, so it cannot automatically change the actual argument order.
   Instead, `tf_upgrade.py` makes your function invocations order-independent
   by introducing keyword arguments.
 * Constructions like `tf.get_variable_scope().reuse_variables()`
   will likely not work. We recommend deleting those lines and replacing
   them with lines such as the following:

   <pre class="prettyprint">
   with tf.variable_scope(tf.get_variable_scope(), reuse=True):
     ...
   </pre>

 * Analogously to `tf.pack` and  `tf.unpack`, we're renamed
   `TensorArray.pack` and `TensorArray.unpack` to
   `TensorArray.stack` and `TensorArray.unstack`. However, `TensorArray.pack`
   and `TensorArray.unpack` cannot be detected lexically since they are
   indirectly related to the <a href="../../api_docs/python/tf.md"><code>tf</code></a> namespace e.g.
   `foo = tf.TensorArray(); foo.unpack()`

<h2 id="Upgrading_your_code_manually">Upgrading your code manually</h2>

Instead of running `tf_upgrade.py`, you may manually upgrade your code.
The remainder of this document provides a comprehensive list of
all backward incompatible changes made in TensorFlow 1.0.


### Variables

Variable functions have been made more consistent and less confusing.

* `tf.VARIABLES`
    * should be renamed to `tf.GLOBAL_VARIABLES`
* <a href="../../api_docs/python/tf/all_variables.md"><code>tf.all_variables</code></a>
    * should be renamed to <a href="../../api_docs/python/tf/global_variables.md"><code>tf.global_variables</code></a>
* <a href="../../api_docs/python/tf/initialize_all_variables.md"><code>tf.initialize_all_variables</code></a>
    * should be renamed to <a href="../../api_docs/python/tf/initializers/global_variables.md"><code>tf.global_variables_initializer</code></a>
* <a href="../../api_docs/python/tf/initialize_local_variables.md"><code>tf.initialize_local_variables</code></a>
    * should be renamed to <a href="../../api_docs/python/tf/initializers/local_variables.md"><code>tf.local_variables_initializer</code></a>
* <a href="../../api_docs/python/tf/initialize_variables.md"><code>tf.initialize_variables</code></a>
    * should be renamed to <a href="../../api_docs/python/tf/initializers/variables.md"><code>tf.variables_initializer</code></a>

### Summary functions

Summary functions have been consolidated under the <a href="../../api_docs/python/tf/summary.md"><code>tf.summary</code></a> namespace.

* `tf.audio_summary`
    * should be renamed to <a href="../../api_docs/python/tf/summary/audio.md"><code>tf.summary.audio</code></a>
* <a href="../../api_docs/python/tf/contrib/deprecated/histogram_summary.md"><code>tf.contrib.deprecated.histogram_summary</code></a>
    * should be renamed to <a href="../../api_docs/python/tf/summary/histogram.md"><code>tf.summary.histogram</code></a>
* <a href="../../api_docs/python/tf/contrib/deprecated/scalar_summary.md"><code>tf.contrib.deprecated.scalar_summary</code></a>
    * should be renamed to <a href="../../api_docs/python/tf/summary/scalar.md"><code>tf.summary.scalar</code></a>
* `tf.histogram_summary`
    * should be renamed to <a href="../../api_docs/python/tf/summary/histogram.md"><code>tf.summary.histogram</code></a>
* `tf.image_summary`
    * should be renamed to <a href="../../api_docs/python/tf/summary/image.md"><code>tf.summary.image</code></a>
* `tf.merge_all_summaries`
    * should be renamed to <a href="../../api_docs/python/tf/summary/merge_all.md"><code>tf.summary.merge_all</code></a>
* `tf.merge_summary`
    * should be renamed to <a href="../../api_docs/python/tf/summary/merge.md"><code>tf.summary.merge</code></a>
* `tf.scalar_summary`
    * should be renamed to <a href="../../api_docs/python/tf/summary/scalar.md"><code>tf.summary.scalar</code></a>
* `tf.train.SummaryWriter`
    * should be renamed to <a href="../../api_docs/python/tf/summary/FileWriter.md"><code>tf.summary.FileWriter</code></a>

### Numeric differences


Integer division and <a href="../../api_docs/python/tf/floordiv.md"><code>tf.floordiv</code></a> now uses flooring semantics. This is to
make the results of `np.divide` and `np.mod` consistent with <a href="../../api_docs/python/tf/divide.md"><code>tf.divide</code></a> and
<a href="../../api_docs/python/tf/floormod.md"><code>tf.mod</code></a>, respectively. In addition we have changed the rounding algorithm
used by <a href="../../api_docs/python/tf/round.md"><code>tf.round</code></a> to match NumPy.


* <a href="../../api_docs/python/tf/div.md"><code>tf.div</code></a>

    * The semantics of <a href="../../api_docs/python/tf/divide.md"><code>tf.divide</code></a> division have been changed to match Python
semantics completely. That is, `/` in Python 3     and future division mode in
Python 2 will produce floating point numbers always, `//` will produce floored
division.     However, even <a href="../../api_docs/python/tf/div.md"><code>tf.div</code></a> will produce floored integer division.
To force C-style truncation semantics, you must use <a href="../../api_docs/python/tf/truncatediv.md"><code>tf.truncatediv</code></a>.

    * Consider changing your code to use <a href="../../api_docs/python/tf/divide.md"><code>tf.divide</code></a>, which follows Python semantics for promotion.

* <a href="../../api_docs/python/tf/floormod.md"><code>tf.mod</code></a>

    * The semantics of <a href="../../api_docs/python/tf/floormod.md"><code>tf.mod</code></a> have been changed to match Python semantics. In
particular, flooring semantics are used for     integers. If you wish to have
C-style truncation mod (remainders), you can use <a href="../../api_docs/python/tf/truncatemod.md"><code>tf.truncatemod</code></a>


The old and new behavior of division can be summarized with this table:

| Expr                | TF 0.11 (py2) | TF 0.11 (py3) | TF 1.0 (py2) | TF 1.0 (py3) |
|---------------------|---------------|---------------|--------------|--------------|
| tf.div(3,4)         | 0             | 0             | 0            | 0            |
| tf.div(-3,4)        | 0             | 0             | -1           | -1           |
| tf.mod(-3,4)        | -3            | -3            | 1            | 1            |
| -3/4                | 0             | -0.75         | -1           | -0.75        |
| -3/4tf.divide(-3,4) | N/A           | N/A           | -0.75        | -1           |

The old and new behavior of rounding can be summarized with this table:

| Input | Python | NumPy | C++ round() | TensorFlow 0.11(floor(x+.5)) | TensorFlow 1.0 |
|-------|--------|-------|-------------|------------------------------|----------------|
| -3.5  | -4     | -4    | -4          | -3                           | -4             |
| -2.5  | -2     | -2    | -3          | -2                           | -2             |
| -1.5  | -2     | -2    | -2          | -1                           | -2             |
| -0.5  | 0      | 0     | -1          | 0                            | 0              |
| 0.5   | 0      | 0     | 1           | 1                            | 0              |
| 1.5   | 2      | 2     | 2           | 2                            | 2              |
| 2.5   | 2      | 2     | 3           | 3                            | 2              |
| 3.5   | 4      | 4     | 4           | 4                            | 4              |



### NumPy matching names


Many functions have been renamed to match NumPy. This was done to make the
transition between NumPy and TensorFlow as easy as possible. There are still
numerous cases where functions do not match, so this is far from a hard and
fast rule, but we have removed several commonly noticed inconsistencies.

* `tf.inv`
    * should be renamed to <a href="../../api_docs/python/tf/math/reciprocal.md"><code>tf.reciprocal</code></a>
    * This was done to avoid confusion with NumPy's matrix inverse `np.inv`
* `tf.list_diff`
    * should be renamed to <a href="../../api_docs/python/tf/setdiff1d.md"><code>tf.setdiff1d</code></a>
* `tf.listdiff`
    * should be renamed to <a href="../../api_docs/python/tf/setdiff1d.md"><code>tf.setdiff1d</code></a>
* `tf.mul`
    * should be renamed to <a href="../../api_docs/python/tf/multiply.md"><code>tf.multiply</code></a>
* `tf.neg`
    * should be renamed to <a href="../../api_docs/python/tf/negative.md"><code>tf.negative</code></a>
* `tf.select`
    * should be renamed to <a href="../../api_docs/python/tf/where.md"><code>tf.where</code></a>
    * <a href="../../api_docs/python/tf/where.md"><code>tf.where</code></a> now takes 3 arguments or 1 argument, just like `np.where`
* `tf.sub`
    * should be renamed to <a href="../../api_docs/python/tf/subtract.md"><code>tf.subtract</code></a>

### NumPy matching arguments

Arguments for certain TensorFlow 1.0 methods now match arguments in certain
NumPy methods.  To achieve this, TensorFlow 1.0 has changed keyword arguments
and reordered some arguments. Notably, TensorFlow 1.0 now uses `axis` rather
than `dimension`. TensorFlow 1.0 aims to keep the tensor argument first on
operations that modify Tensors. (see the <a href="../../api_docs/python/tf/concat.md"><code>tf.concat</code></a> change).


* <a href="../../api_docs/python/tf/argmax.md"><code>tf.argmax</code></a>
    * keyword argument `dimension` should be renamed to `axis`
* <a href="../../api_docs/python/tf/argmin.md"><code>tf.argmin</code></a>
    * keyword argument `dimension` should be renamed to `axis`
* <a href="../../api_docs/python/tf/concat.md"><code>tf.concat</code></a>
    * keyword argument `concat_dim` should be renamed to `axis`
    * arguments have been reordered to `tf.concat(values, axis, name='concat')`.
* <a href="../../api_docs/python/tf/count_nonzero.md"><code>tf.count_nonzero</code></a>
    * keyword argument `reduction_indices` should be renamed to `axis`
* <a href="../../api_docs/python/tf/expand_dims.md"><code>tf.expand_dims</code></a>
    * keyword argument `dim` should be renamed to `axis`
* <a href="../../api_docs/python/tf/reduce_all.md"><code>tf.reduce_all</code></a>
    * keyword argument `reduction_indices` should be renamed to `axis`
* <a href="../../api_docs/python/tf/reduce_any.md"><code>tf.reduce_any</code></a>
    * keyword argument `reduction_indices` should be renamed to `axis`
* <a href="../../api_docs/python/tf/reduce_join.md"><code>tf.reduce_join</code></a>
    * keyword argument `reduction_indices` should be renamed to `axis`
* <a href="../../api_docs/python/tf/reduce_logsumexp.md"><code>tf.reduce_logsumexp</code></a>
    * keyword argument `reduction_indices` should be renamed to `axis`
* <a href="../../api_docs/python/tf/reduce_max.md"><code>tf.reduce_max</code></a>
    * keyword argument `reduction_indices` should be renamed to `axis`
* <a href="../../api_docs/python/tf/reduce_mean.md"><code>tf.reduce_mean</code></a>
    * keyword argument `reduction_indices` should be renamed to `axis`
* <a href="../../api_docs/python/tf/reduce_min.md"><code>tf.reduce_min</code></a>
    * keyword argument `reduction_indices` should be renamed to `axis`
* <a href="../../api_docs/python/tf/reduce_prod.md"><code>tf.reduce_prod</code></a>
    * keyword argument `reduction_indices` should be renamed to `axis`
* <a href="../../api_docs/python/tf/reduce_sum.md"><code>tf.reduce_sum</code></a>
    * keyword argument `reduction_indices` should be renamed to `axis`
* <a href="../../api_docs/python/tf/manip/reverse.md"><code>tf.reverse</code></a>
    * <a href="../../api_docs/python/tf/manip/reverse.md"><code>tf.reverse</code></a> used to take a 1D `bool` tensor to control which dimensions were reversed. Now we use a Tensor of axis indices.
    * For example `tf.reverse(a, [True, False, True])` now must be `tf.reverse(a, [0, 2])`
* <a href="../../api_docs/python/tf/reverse_sequence.md"><code>tf.reverse_sequence</code></a>
    * keyword argument `batch_dim` should be renamed to `batch_axis`
    * keyword argument `seq_dim` should be renamed to `seq_axis`
* <a href="../../api_docs/python/tf/sparse_concat.md"><code>tf.sparse_concat</code></a>
    * keyword argument `concat_dim` should be renamed to `axis`
* <a href="../../api_docs/python/tf/sparse_reduce_sum.md"><code>tf.sparse_reduce_sum</code></a>
    * keyword argument `reduction_axes` should be renamed to `axis`
* <a href="../../api_docs/python/tf/sparse_reduce_sum_sparse.md"><code>tf.sparse_reduce_sum_sparse</code></a>
    * keyword argument `reduction_axes` should be renamed to `axis`
* <a href="../../api_docs/python/tf/sparse_split.md"><code>tf.sparse_split</code></a>
    * keyword argument `split_dim` should be renamed to `axis`
    * arguments have been reordered to `tf.sparse_split(keyword_required=KeywordRequired(), sp_input=None, num_split=None, axis=None, name=None, split_dim=None)`.
* <a href="../../api_docs/python/tf/split.md"><code>tf.split</code></a>
    * keyword argument `split_dim` should be renamed to `axis`
    * keyword argument `num_split` should be renamed to `num_or_size_splits`
    * arguments have been reordered to `tf.split(value, num_or_size_splits, axis=0, num=None, name='split')`.
* <a href="../../api_docs/python/tf/squeeze.md"><code>tf.squeeze</code></a>
    * keyword argument `squeeze_dims` should be renamed to `axis`
* <a href="../../api_docs/python/tf/svd.md"><code>tf.svd</code></a>
    * arguments have been reordered to `tf.svd(tensor, full_matrices=False, compute_uv=True, name=None)`.

### Simplified math variants

Batched versions of math operations have been removed. Now the functionality is
contained in the non-batched versions. Similarly,`tf.complex_abs` has had its
functionality moved to <a href="../../api_docs/python/tf/abs.md"><code>tf.abs</code></a>

* `tf.batch_band_part`
    * should be renamed to `tf.band_part`
* `tf.batch_cholesky`
    * should be renamed to <a href="../../api_docs/python/tf/linalg/cholesky.md"><code>tf.cholesky</code></a>
* `tf.batch_cholesky_solve`
    * should be renamed to <a href="../../api_docs/python/tf/cholesky_solve.md"><code>tf.cholesky_solve</code></a>
* `tf.batch_fft`
    * should be renamed to <a href="../../api_docs/python/tf/spectral/fft.md"><code>tf.fft</code></a>
* `tf.batch_fft3d`
    * should be renamed to <a href="../../api_docs/python/tf/spectral/fft3d.md"><code>tf.fft3d</code></a>
* `tf.batch_ifft`
    * should be renamed to <a href="../../api_docs/python/tf/spectral/ifft.md"><code>tf.ifft</code></a>
* `tf.batch_ifft2d`
    * should be renamed to <a href="../../api_docs/python/tf/spectral/ifft2d.md"><code>tf.ifft2d</code></a>
* `tf.batch_ifft3d`
    * should be renamed to <a href="../../api_docs/python/tf/spectral/ifft3d.md"><code>tf.ifft3d</code></a>
* `tf.batch_matmul`
    * should be renamed to <a href="../../api_docs/python/tf/matmul.md"><code>tf.matmul</code></a>
* `tf.batch_matrix_determinant`
    * should be renamed to <a href="../../api_docs/python/tf/linalg/det.md"><code>tf.matrix_determinant</code></a>
* `tf.batch_matrix_diag`
    * should be renamed to <a href="../../api_docs/python/tf/linalg/diag.md"><code>tf.matrix_diag</code></a>
* `tf.batch_matrix_inverse`
    * should be renamed to <a href="../../api_docs/python/tf/linalg/inv.md"><code>tf.matrix_inverse</code></a>
* `tf.batch_matrix_solve`
    * should be renamed to <a href="../../api_docs/python/tf/linalg/solve.md"><code>tf.matrix_solve</code></a>
* `tf.batch_matrix_solve_ls`
    * should be renamed to <a href="../../api_docs/python/tf/matrix_solve_ls.md"><code>tf.matrix_solve_ls</code></a>
* `tf.batch_matrix_transpose`
    * should be renamed to <a href="../../api_docs/python/tf/matrix_transpose.md"><code>tf.matrix_transpose</code></a>
* `tf.batch_matrix_triangular_solve`
    * should be renamed to <a href="../../api_docs/python/tf/linalg/triangular_solve.md"><code>tf.matrix_triangular_solve</code></a>
* `tf.batch_self_adjoint_eig`
    * should be renamed to <a href="../../api_docs/python/tf/self_adjoint_eig.md"><code>tf.self_adjoint_eig</code></a>
* `tf.batch_self_adjoint_eigvals`
    * should be renamed to <a href="../../api_docs/python/tf/self_adjoint_eigvals.md"><code>tf.self_adjoint_eigvals</code></a>
* `tf.batch_set_diag`
    * should be renamed to `tf.set_diag`
* `tf.batch_svd`
    * should be renamed to <a href="../../api_docs/python/tf/svd.md"><code>tf.svd</code></a>
* `tf.complex_abs`
    * should be renamed to <a href="../../api_docs/python/tf/abs.md"><code>tf.abs</code></a>

### Misc Changes

Several other changes have been made, including the following:

* `tf.image.per_image_whitening`
    * should be renamed to <a href="../../api_docs/python/tf/image/per_image_standardization.md"><code>tf.image.per_image_standardization</code></a>
* <a href="../../api_docs/python/tf/nn/sigmoid_cross_entropy_with_logits.md"><code>tf.nn.sigmoid_cross_entropy_with_logits</code></a>
    * arguments have been reordered to `tf.nn.sigmoid_cross_entropy_with_logits(_sentinel=None, labels=None, logits=None, name=None)`.
* <a href="../../api_docs/python/tf/nn/softmax_cross_entropy_with_logits.md"><code>tf.nn.softmax_cross_entropy_with_logits</code></a>
    * arguments have been reordered to `tf.nn.softmax_cross_entropy_with_logits(_sentinel=None, labels=None, logits=None, dim=-1, name=None)`.
* <a href="../../api_docs/python/tf/nn/sparse_softmax_cross_entropy_with_logits.md"><code>tf.nn.sparse_softmax_cross_entropy_with_logits</code></a>
    * arguments have been reordered to `tf.nn.sparse_softmax_cross_entropy_with_logits(_sentinel=None, labels=None, logits=None, name=None)`.
* <a href="../../api_docs/python/tf/keras/initializers/Ones.md"><code>tf.ones_initializer</code></a>
    * should be changed to a function call i.e. `tf.ones_initializer()`
* `tf.pack`
    * should be renamed to <a href="../../api_docs/python/tf/stack.md"><code>tf.stack</code></a>
* <a href="../../api_docs/python/tf/round.md"><code>tf.round</code></a>
    * The semantics of <a href="../../api_docs/python/tf/round.md"><code>tf.round</code></a> now match Banker's rounding.
* `tf.unpack`
    * should be renamed to <a href="../../api_docs/python/tf/unstack.md"><code>tf.unstack</code></a>
* <a href="../../api_docs/python/tf/keras/initializers/Zeros.md"><code>tf.zeros_initializer</code></a>
    * should be changed to a function call i.e. `tf.zeros_initializer()`
