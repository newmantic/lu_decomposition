# lu_decomposition


LU Decomposition is a matrix factorization technique that decomposes a matrix A into the product of two matrices: a lower triangular matrix L and an upper triangular matrix U. This decomposition is useful for solving linear 


Matrix A:
Let A be an n x n square matrix. LU decomposition expresses A as:
A = L * U
Where:
L is an n x n lower triangular matrix.
U is an n x n upper triangular matrix.

Lower Triangular Matrix L:
A lower triangular matrix L is a matrix where all the elements above the main diagonal are zero. The diagonal elements are typically set to 1 in Doolittle's method:
L = [ l11  0   0  ...  0  ]
    [ l21 l22  0  ...  0  ]
    [ l31 l32 l33 ...  0  ]
    [  .   .   .  ...  .  ]
    [ ln1 ln2 ln3 ... lnn ]
    
Upper Triangular Matrix U:
An upper triangular matrix U is a matrix where all the elements below the main diagonal are zero:
U = [ u11 u12 u13 ... u1n ]
    [  0  u22 u23 ... u2n ]
    [  0   0  u33 ... u3n ]
    [  .   .   .  ...  .  ]
    [  0   0   0  ... unn ]


Doolittle's method is a specific algorithm for performing LU decomposition. It produces a lower triangular matrix L with 1s on the diagonal and an upper triangular matrix U.

Initialize:
Start with matrices L and U as zero matrices.

Construct U:
For each row i, calculate the elements of U by subtracting the products of corresponding elements of L and U from the elements of A:
U[i, k] = A[i, k] - sum(L[i, j] * U[j, k]) for j = 1 to i-1

Construct L:
For each column k, calculate the elements of L by subtracting the products of corresponding elements of L and U from the elements of A, then dividing by the diagonal element of U:
L[k, i] = (A[k, i] - sum(L[k, j] * U[j, i]) for j = 1 to i-1) / U[i, i]
Set L[i, i] = 1 for all i.
