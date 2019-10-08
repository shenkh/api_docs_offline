<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.linalg.set_diag" />
<meta itemprop="path" content="Stable" />
</div>

# tf.linalg.set_diag

``` python
tf.linalg.set_diag(
    input,
    diagonal,
    name='set_diag',
    k=0
)
```



Defined in [`tensorflow/python/ops/array_ops.py`](/code/stable/tensorflow/python/ops/array_ops.py).

Returns a batched matrix tensor with new batched diagonal values.

Given `input` and `diagonal`, this operation returns a tensor with the
same shape and values as `input`, except for the specified diagonals of the
innermost matrices. These will be overwritten by the values in `diagonal`.

`input` has `r+1` dimensions `[I, J, ..., L, M, N]`. When `k` is scalar or
`k[0] == k[1]`, `diagonal` has `r` dimensions `[I, J, ..., L, max_diag_len]`.
Otherwise, it has `r+1` dimensions `[I, J, ..., L, num_diags, max_diag_len]`.
`num_diags` is the number of diagonals, `num_diags = k[1] - k[0] + 1`.
`max_diag_len` is the longest diagonal in the range `[k[0], k[1]]`,
`max_diag_len = min(M + min(k[1], 0), N + min(-k[0], 0))`

The output is a tensor of rank `k+1` with dimensions `[I, J, ..., L, M, N]`.
If `k` is scalar or `k[0] == k[1]`:

```
output[i, j, ..., l, m, n]
  = diagonal[i, j, ..., l, n-max(k[1], 0)] ; if n - m == k[1]
    output[i, j, ..., l, m, n]             ; otherwise
```

Otherwise,

```
output[i, j, ..., l, m, n]
  = diagonal[i, j, ..., l, k[1]-d, n-max(d, 0)] ; if d_lower <= d <= d_upper
    input[i, j, ..., l, m, n]                   ; otherwise
```
where `d = n - m`

For example:

```
# The main diagonal.
input = np.array([[[7, 7, 7, 7],              # Input shape: (2, 3, 4)
                   [7, 7, 7, 7],
                   [7, 7, 7, 7]],
                  [[7, 7, 7, 7],
                   [7, 7, 7, 7],
                   [7, 7, 7, 7]]])
diagonal = np.array([[1, 2, 3],               # Diagonal shape: (2, 3)
                     [4, 5, 6]])
tf.matrix_diag(diagonal) ==> [[[1, 7, 7, 7],  # Output shape: (2, 3, 4)
                               [7, 2, 7, 7],
                               [7, 7, 3, 7]],
                              [[4, 7, 7, 7],
                               [7, 5, 7, 7],
                               [7, 7, 6, 7]]]

# A superdiagonal (per batch).
tf.matrix_diag(diagonal, k = 1)
  ==> [[[7, 1, 7, 7],  # Output shape: (2, 3, 4)
        [7, 7, 2, 7],
        [7, 7, 7, 3]],
       [[7, 4, 7, 7],
        [7, 7, 5, 7],
        [7, 7, 7, 6]]]

# A band of diagonals.
diagonals = np.array([[[1, 2, 3],  # Diagonal shape: (2, 2, 3)
                       [4, 5, 0]],
                      [[6, 1, 2],
                       [3, 4, 0]]])
tf.matrix_diag(diagonals, k = (-1, 0))
  ==> [[[1, 7, 7, 7],  # Output shape: (2, 3, 4)
        [4, 2, 7, 7],
        [0, 5, 3, 7]],
       [[6, 7, 7, 7],
        [3, 1, 7, 7],
        [7, 4, 2, 7]]]

```

#### Args:

* <b>`input`</b>: A `Tensor` with rank `k + 1`, where `k >= 1`.
* <b>`diagonal`</b>:  A `Tensor` with rank `k`, when `d_lower == d_upper`, or `k + 1`,
    otherwise. `k >= 1`.
* <b>`name`</b>: A name for the operation (optional).
* <b>`k`</b>: Diagonal offset(s). Positive value means superdiagonal, 0 refers to the
    main diagonal, and negative value means subdiagonals. `k` can be a single
    integer (for a single diagonal) or a pair of integers specifying the low
    and high ends of a matrix band. `k[0]` must not be larger than `k[1]`.