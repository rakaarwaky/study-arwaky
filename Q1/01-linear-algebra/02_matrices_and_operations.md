# Matrices and Their Operations

## Abstract

This article develops matrices as rectangular arrays of scalars and the
operations that act on them. It proceeds from matrix dimensions and special
types, through addition, scalar multiplication, multiplication, transpose,
and block partitioning, to a survey of standard matrix classes. Every
section states the definition, the principal identities, a worked example,
and an exercise. The article covers the full S02 module checklist of 42
concepts across 6 subtopics.

**Keywords:** matrix, dimension, zero matrix, identity matrix, scalar,
matrix addition, matrix multiplication, transpose, symmetric matrix,
skew-symmetric matrix, orthogonal matrix, block matrix, partition, diagonal,
triangular, idempotent, nilpotent.

---

## 1. Matrix Fundamentals

A matrix is a rectangular array of scalars arranged in rows and columns. An
m×n matrix A has m rows and n columns, written A = [aᵢⱼ] where aᵢⱼ is the
entry in row i and column j. Matrices are added componentwise and multiplied
by scalars componentwise; two matrices are equal exactly when they have the
same dimensions and equal corresponding entries.

**Matrix dimension definition.** The dimensions of an m×n matrix are m rows
by n columns. Only matrices of the same dimensions can be added or compared
for equality. A square matrix has m = n.

**Special matrix types.** Common special matrices include the square matrix
(m = n), diagonal matrix (nonzero entries only on the main diagonal),
scalar matrix (diagonal matrix with equal diagonal entries), and identity
matrix Iₙ (diagonal entries all 1, all others 0).

**Zero matrix properties.** The zero matrix 0ₘ×ₙ has every entry equal to 0.
It is the additive identity: A + 0 = 0 + A = A for any m×n matrix A, and
c·0 = 0 for any scalar c.

**Identity matrix properties.** The identity matrix Iₙ acts as the
multiplicative identity: A Iₙ = A and Iₙ A = A whenever the products are
defined. It is diagonal with 1s on the diagonal.

**Scalar matrix operations.** Multiplying a matrix by a scalar c scales
every entry: (cA)ᵢⱼ = c·aᵢⱼ. Scalar multiplication distributes over matrix
addition: c(A + B) = cA + cB, and over scalar addition: (c + d)A = cA + dA.

**Matrix equality criteria.** Two matrices A and B are equal when they have
the same dimensions and aᵢⱼ = bᵢⱼ for every i, j.

**Partitioned matrices.** A partitioned matrix is written as a block array
of submatrices. Partitioning does not change the underlying matrix; it only
groups entries for easier reasoning about products and sums.

**Worked example.** Let A = [[1, 2, 3], [4, 5, 6]] be a 2×3 matrix and B =
[[7, 8], [9, 10], [11, 12]] be a 3×2 matrix. Then A has dimensions 2×3,
B has dimensions 3×2, and AB is defined and is a 2×2 matrix. BA is defined
and is a 3×3 matrix. A + B is undefined because the dimensions differ.

**Exercises.**
1. State the dimensions of [[1, 2], [3, 4], [5, 6]] and of its transpose.
2. For A = [[2, 0], [0, 3]], find 3A and A + 2A.
3. Show that A + 0 = A for A = [[1, 2], [3, 4]].

---

## 2. Matrix Addition

Matrix addition is defined componentwise for matrices of the same
dimensions. If A = [aᵢⱼ] and B = [bᵢⱼ] are both m×n, then A + B =
[aᵢⱼ + bᵢⱼ]. Subtraction follows the same rule: A − B = [aᵢⱼ − bᵢⱼ].

**Matrix addition rules.** Addition is componentwise: (A + B)ᵢⱼ = aᵢⱼ +
bᵢⱼ. The sum is defined only when A and B have identical dimensions.

**Matrix subtraction rules.** Subtraction is componentwise: (A − B)ᵢⱼ =
aᵢⱼ − bᵢⱼ. Like addition, it requires identical dimensions.

**Commutative property of addition.** A + B = B + A for all m×n matrices A,
B, because scalar addition is commutative.

**Associative property of addition.** (A + B) + C = A + (B + C) whenever
all three matrices share the same dimensions.

**Zero matrix as identity.** 0 + A = A + 0 = A for every m×n matrix A.

**Additive inverse matrices.** For every m×n matrix A there is −A with
entries (−aᵢⱼ) such that A + (−A) = 0.

**Dimensions compatibility check.** Before adding or subtracting, confirm
that both operands have the same number of rows and columns; otherwise the
operation is undefined.

**Worked example.** A = [[1, 2], [3, 4]] and B = [[5, 6], [7, 8]] give
A + B = [[6, 8], [10, 12]] and A − B = [[−4, −4], [−4, −4]].

**Exercises.**
1. Compute [[1, 2], [3, 4]] + [[5, 6], [7, 8]].
2. Is [[1, 2]] + [[3], [4]] defined? Explain.
3. Find −A for A = [[0, −1], [2, 3]].

---

## 3. Matrix Multiplication

The product AB of an m×k matrix A and a k×n matrix B is the m×n matrix C
with cᵢⱼ = Σₗ₌₁ᵏ aᵢₗ bₗⱼ — the dot product of row i of A with column j of B.
Multiplication is defined only when the inner dimensions match.

**Multiplication compatibility rules.** AB is defined when A is m×k and B
is k×n; the result is m×n. The number of columns of A must equal the number
of rows of B.

**Row-column product method.** Entry cᵢⱼ of AB equals row i of A dotted
with column j of B: cᵢⱼ = aᵢ₁b₁ⱼ + aᵢ₂b₂ⱼ + … + aᵢₖbₖⱼ.

**Non-commutative property.** In general AB ≠ BA. Even when both products
are defined, they may have different dimensions or different entries.

**Associative property of multiplication.** (AB)C = A(BC) whenever the
products are defined.

**Distributive property over addition.** A(B + C) = AB + AC and
(A + B)C = AC + BC whenever defined.

**Identity matrix multiplication.** AIₙ = A and IₘA = A whenever defined;
Iₙ is the multiplicative identity for n×n matrices.

**Powers of square matrices.** For a square matrix A, A² = AA, A³ = AAA,
and so on. A⁰ = Iₙ by convention.

**Worked example.** A = [[1, 2], [3, 4]] and B = [[5, 6], [7, 8]] give
AB = [[1·5+2·7, 1·6+2·8], [3·5+4·7, 3·6+4·8]] = [[19, 22], [43, 50]].
BA = [[23, 34], [31, 46]] ≠ AB, showing non-commutativity.

**Exercises.**
1. Compute [[1, 2], [3, 4]] · [[5, 6], [7, 8]].
2. For A = [[1, 2, 3]] (1×3) and B = [[4], [5], [6]] (3×1), compute AB
   and BA.
3. Show (AB)ᵀ = BᵀAᵀ for 2×2 matrices A, B of your choice.

---

## 4. Matrix Transpose

The transpose Aᵀ of an m×n matrix A is the n×m matrix whose (i, j) entry
is aⱼᵢ — rows become columns and columns become rows.

**Transpose operation definition.** (Aᵀ)ᵢⱼ = aⱼᵢ. If A is m×n then Aᵀ is
n×m.

**Transpose of sum property.** (A + B)ᵀ = Aᵀ + Bᵀ whenever A and B have
the same dimensions.

**Transpose of product property.** (AB)ᵀ = BᵀAᵀ whenever AB is defined —
the order reverses.

**Symmetric matrix identification.** A square matrix A is symmetric when
A = Aᵀ, i.e. aᵢⱼ = aⱼᵢ for all i, j.

**Skew-symmetric matrices.** A square matrix A is skew-symmetric when
Aᵀ = −A, so aᵢⱼ = −aⱼᵢ and all diagonal entries are 0.

**Orthogonal matrix properties.** A square matrix Q is orthogonal when
QᵀQ = I, equivalently Q⁻¹ = Qᵀ. Its columns (and rows) form an orthonormal
set.

**Trace of matrix.** The trace of a square matrix A is tr(A) = Σᵢ aᵢᵢ, the
sum of its diagonal entries. tr(A + B) = tr(A) + tr(B) and tr(AB) = tr(BA).

**Worked example.** A = [[1, 2, 3], [4, 5, 6]] is 2×3; Aᵀ =
[[1, 4], [2, 5], [3, 6]] is 3×2. tr([[1, 2], [3, 4]]) = 1 + 4 = 5.

**Exercises.**
1. Find the transpose of [[1, 2, 3], [4, 5, 6]].
2. Show that (A + B)ᵀ = Aᵀ + Bᵀ for 2×2 matrices.
3. Is [[0, 1], [−1, 0]] symmetric, skew-symmetric, or neither?

---

## 5. Block Matrices

A block matrix partitions a matrix into submatrices (blocks) arranged in a
grid. Block operations follow the same algebraic rules as scalar operations,
provided the block dimensions are compatible.

**Block matrix multiplication.** If A and B are partitioned conformably,
then (AB)ᵢⱼ = Σₖ AᵢₖBₖⱼ where each term is a block product.

**Block diagonal matrices.** A block diagonal matrix has square blocks on
the diagonal and zero blocks elsewhere. Its determinant is the product of
the block determinants.

**Block triangular matrices.** A block triangular matrix has zero blocks
below (upper) or above (lower) the diagonal. Its inverse is block
triangular when the diagonal blocks are invertible.

**Inversion of block matrices.** For [[A, B], [0, D]] with A and D
invertible, the inverse is [[A⁻¹, −A⁻¹BD⁻¹], [0, D⁻¹]].

**Determinant of partitioned matrices.** For a block diagonal matrix,
det = det(A₁)det(A₂)…det(Aₖ). For triangular block matrices, similar
products hold.

**Kronecker product definition.** The Kronecker product A ⊗ B of an m×n
matrix A and a p×q matrix B is the mp×nq block matrix whose (i, j) block is
aᵢⱼB.

**Hadamard product definition.** The Hadamard (entrywise) product A ∘ B of
two same-dimension matrices has entries (aᵢⱼbᵢⱼ).

**Worked example.** A = [[1, 2], [3, 4]] partitioned as blocks [[1], [3]],
[[2], [4]]; B = [[5, 6]] partitioned [[5, 6]]. AB = [[5, 6], [15, 18]] via
block row-column products.

**Exercises.**
1. Partition [[1, 2, 3], [4, 5, 6], [7, 8, 9]] into four blocks and
   multiply by [[1, 0], [0, 1]] viewed as conformable blocks.
2. Compute A ⊗ B for A = [[1, 2]], B = [[3], [4]].
3. Compute A ∘ B for A = [[1, 2]], B = [[3, 4]].

---

## 6. Matrix Types

Beyond the special types above, several named matrix classes recur
throughout linear algebra and its applications.

**Diagonal matrices.** A diagonal matrix has nonzero entries only on the
main diagonal. Powers and products of diagonal matrices are diagonal.

**Triangular matrices.** An upper triangular matrix has zeros below the
diagonal; a lower triangular matrix has zeros above it. The determinant of
a triangular matrix is the product of its diagonal entries.

**Symmetric matrices.** A = Aᵀ. Symmetric matrices have real eigenvalues
and orthogonal eigenvectors (spectral theorem).

**Skew-symmetric matrices.** Aᵀ = −A. Diagonal entries are 0; eigenvalues
are purely imaginary or zero.

**Idempotent matrices.** A² = A. Projection matrices are idempotent.

**Nilpotent matrices.** Aᵏ = 0 for some k ≥ 1. All eigenvalues are 0.

**Orthogonal matrices.** QᵀQ = I. Orthogonal matrices preserve lengths and
angles; their determinant is ±1.

**Worked example.** A = [[1, 0], [0, 0]] is idempotent since A² = A. Q =
[[0, −1], [1, 0]] is orthogonal since QᵀQ = I₂. N = [[0, 1], [0, 0]] is
nilpotent since N² = 0.

**Exercises.**
1. Show that a diagonal matrix with entries d₁, …, dₙ satisfies Aᵏ =
   diag(d₁ᵏ, …, dₙᵏ).
2. Find an example of a non-zero nilpotent 2×2 matrix.
3. Show that Q = [[0, −1], [1, 0]] is orthogonal and compute det(Q).

---

## References

The sources for this section are the same standard references used across
the linear algebra field doc: Khan Academy Linear Algebra, MIT OpenCourseWare
18.06 (Gilbert Strang), 3Blue1Brown linear algebra series, and standard
texts such as "Linear Algebra and Its Applications" (Lay) and "Introduction
to Linear Algebra" (Strang). Specific entries: matrix multiplication,
transpose, symmetric matrix, orthogonal matrix, trace, Kronecker product on
Wikipedia and MathWorld; block matrix inversion formulas from standard
linear algebra references.
