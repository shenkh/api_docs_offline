# Linear Algebra (contrib)
[TOC]

Linear algebra libraries for TensorFlow.

<h2 id="_LinearOperator_">`LinearOperator`</h2>

Subclasses of `LinearOperator` provide a access to common methods on a
(batch) matrix, without the need to materialize the matrix.  This allows:

* Matrix free computations
* Different operators to take advantage of special structure, while providing a
  consistent API to users.

### Base class

*   <a href="../../api_docs/python/tf/linalg/LinearOperator.md"><code>tf.contrib.linalg.LinearOperator</code></a>

### Individual operators

*   <a href="../../api_docs/python/tf/linalg/LinearOperatorDiag.md"><code>tf.contrib.linalg.LinearOperatorDiag</code></a>
*   <a href="../../api_docs/python/tf/linalg/LinearOperatorIdentity.md"><code>tf.contrib.linalg.LinearOperatorIdentity</code></a>
*   <a href="../../api_docs/python/tf/linalg/LinearOperatorScaledIdentity.md"><code>tf.contrib.linalg.LinearOperatorScaledIdentity</code></a>
*   <a href="../../api_docs/python/tf/linalg/LinearOperatorFullMatrix.md"><code>tf.contrib.linalg.LinearOperatorFullMatrix</code></a>
*   <a href="../../api_docs/python/tf/linalg/LinearOperatorLowerTriangular.md"><code>tf.contrib.linalg.LinearOperatorLowerTriangular</code></a>
*   <a href="../../api_docs/python/tf/linalg/LinearOperatorLowRankUpdate.md"><code>tf.contrib.linalg.LinearOperatorLowRankUpdate</code></a>

### Transformations and Combinations of operators

*   <a href="../../api_docs/python/tf/linalg/LinearOperatorComposition.md"><code>tf.contrib.linalg.LinearOperatorComposition</code></a>
