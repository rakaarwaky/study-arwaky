# Matrix Factorizations

## Abstract

This article develops the major matrix factorizations: LU, Cholesky,
spectral decomposition, SVD, and their use in PCA. Every section states the
definition, the principal identities, a worked example, and an exercise.
The article covers the full S08 module checklist of 35 concepts across 5
subtopics.

**Keywords:** LU decomposition, Doolittle, Crout, permutation matrix,
Cholesky, positive definite, spectral theorem, singular value decomposition,
singular values, principal component analysis, low-rank approximation.

---

## 1. LU Decomposition

LU factors a square matrix into a lower triangular L and an upper triangular
U, the computational core of Gaussian elimination.

**LU factorization definition.** A = LU where L is unit lower triangular
(1s on diagonal) and U is upper triangular; exists when no row swaps are
needed.

**Doolittle algorithm method.** L has 1s on the diagonal; compute L and U
row by row: lᵢⱼ = (aᵢⱼ − Σₖ<ⱼ lᵢₖuₖⱼ)/uⱼⱼ, uᵢⱼ = aᵢⱼ − Σₖ<ᵢ lᵢₖuₖⱼ.

**Crout algorithm method.** U has 1s on the diagonal; symmetric to
Doolittle with roles of L and U swapped.

**Lower triangular matrix L.** Entries above the diagonal are 0; in LU, L
stores the elimination multipliers below the diagonal.

**Upper triangular matrix U.** Entries below the diagonal are 0; U is the
row echelon form from Gaussian elimination without pivoting.

**Permutation matrix P.** PA = LU form when row swaps are needed; P swaps
rows so that pivots are nonzero (partial pivoting).

**Solving systems using LU.** Ax = b → LUx = b → solve Ly = b by forward
substitution, then Ux = y by back substitution.

**Worked example.** A = [[2, 3], [4, 7]]. Elimination: row2 − 2·row1 →
[[2, 3], [0, 1]] = U, multiplier l₂₁ = 2 → L = [[1, 0], [2, 1]]. Check
LU = [[2, 3], [4, 7]] = A. Solve Ax = [5, 11]: Ly = [5, 11] → y = [5, 1];
Ux = [5, 1] → x = [1, 1].

**Exercises.**
1. Find LU of [[4, 3], [6, 3]] without pivoting.
2. Solve [[2, 3], [4, 7]]x = [5, 11] via LU.
3. When does LU fail without a permutation matrix?

---

## 2. Cholesky Decomposition

Cholesky factors a symmetric positive-definite matrix into LLᵀ, roughly
twice as fast as LU.

**Cholesky factorization definition.** A = LLᵀ where L is lower triangular
with positive diagonal; requires A symmetric positive definite.

**Positive definiteness requirement.** A must be symmetric with all
eigenvalues > 0 (equiv. xᵀAx > 0 for all x ≠ 0, or all leading minors > 0).

**Lower triangular factor L.** Computed column by column: lⱼⱼ =
√(aⱼⱼ − Σₖ<ⱼ lⱼₖ²), lᵢⱼ = (aᵢⱼ − Σₖ<ⱼ lᵢₖlⱼₖ)/lⱼⱼ for i > j.

**Algorithm for Cholesky factors.** The recursive formulas above give L in
O(n³/3) flops — about half the cost of LU.

**Computational efficiency benefits.** Cholesky needs no pivoting (stability
guaranteed by positive definiteness) and ~half the operations of LU.

**Applications in statistics.** Covariance matrices are SPD; Cholesky is
used to generate correlated random variables: x = Lz with z ~ N(0, I).

**Solving normal equations.** AᵀAx = Aᵀb where AᵀA is SPD — solve via
Cholesky instead of forming the inverse.

**Worked example.** A = [[4, 12], [12, 37]] is SPD. l₁₁ = 2, l₂₁ = 6,
l₂₂ = √(37 − 36) = 1 → L = [[2, 0], [6, 1]]. Check LLᵀ =
[[4, 12], [12, 37]] = A.

**Exercises.**
1. Find Cholesky L of [[4, 2], [2, 5]].
2. Verify A = [[4, 12], [12, 37]] is positive definite.
3. Solve [[4, 12], [12, 37]]x = [8, 74] via Cholesky.

---

## 3. Spectral Decomposition

The spectral theorem orthogonally diagonalizes symmetric matrices, the
foundation of PCA and many analyses.

**Spectral theorem statement.** Every real symmetric matrix A is orthogonally
diagonalizable: A = QΛQᵀ with Q orthogonal and Λ real diagonal.

**Orthogonal diagonalizability.** A = QΛQᵀ where columns of Q are orthonormal
eigenvectors and Λ holds the real eigenvalues.

**Eigendecomposition of symmetric matrices.** A = Σᵢ λᵢqᵢqᵢᵀ — a sum of
rank-1 projections scaled by eigenvalues.

**Spectral projection operators.** Pᵢ = qᵢqᵢᵀ projects onto the eigenspace
of λᵢ; A = Σᵢ λᵢPᵢ and the Pᵢ are mutually orthogonal projections.

**Principal component analysis foundation.** PCA diagonalizes the covariance
matrix: principal components are eigenvectors ordered by eigenvalue.

**Matrix norm via eigenvalues.** The spectral norm ‖A‖₂ = maxᵢ |λᵢ| for
symmetric A; equals the largest singular value in general.

**Rayleigh quotient properties.** R(x) = (xᵀAx)/(xᵀx); min/max over x ≠ 0
equal the smallest/largest eigenvalue (Rayleigh-Ritz).

**Worked example.** A = [[3, 1], [1, 3]]: eigenvalues 4, 2 with eigenvectors
(1, 1)/√2, (1, −1)/√2. A = QΛQᵀ with Q = [[1/√2, 1/√2], [1/√2, −1/√2]],
Λ = [[4, 0], [0, 2]].

**Exercises.**
1. Orthogonally diagonalize [[3, 1], [1, 3]].
2. Find eigenvalues of [[2, 1], [1, 2]] and spectral norm.
3. Compute Rayleigh quotient of A = [[3, 1], [1, 3]] at x = (1, 1).

---

## 4. Singular Value Decomposition

SVD factors any matrix into UΣVᵀ, revealing rank, range, and optimal
low-rank approximations.

**SVD definition and existence.** Every m×n matrix A has A = UΣVᵀ with U
(m×m), V (n×n) orthogonal and Σ (m×n) diagonal with nonnegative entries.

**Singular values calculation.** Diagonal entries σ₁ ≥ σ₂ ≥ … ≥ 0 of Σ;
σᵢ² are eigenvalues of AᵀA (or AAᵀ).

**Left singular vectors.** Columns of U; eigenvectors of AAᵀ.

**Right singular vectors.** Columns of V; eigenvectors of AᵀA.

**SVD matrix representation.** A = Σᵢ σᵢuᵢvᵢᵀ — a sum of rank-1 matrices
weighted by singular values.

**Relation to eigendecomposition.** For symmetric PSD A, SVD = spectral
decomposition; singular values = eigenvalues.

**Low-rank matrix approximation.** Aₖ = Σᵢ₌₁ᵏ σᵢuᵢvᵢᵀ is the best rank-k
approximation to A in both 2-norm and Frobenius norm (Eckart-Young).

**Worked example.** A = [[1, 0], [0, 0]]. AᵀA = A → eigenvalues 1, 0 → σ =
(1, 0). V = I, U = I, Σ = [[1, 0], [0, 0]]. A = UΣVᵀ = [[1, 0], [0, 0]].

**Exercises.**
1. Find singular values of [[1, 0], [0, 2]].
2. Compute SVD of [[1, 0], [0, 0]].
3. Find the best rank-1 approximation of diag(3, 2, 1).

---

## 5. Principal Component Analysis

PCA uses the spectral decomposition of the covariance matrix for
dimensionality reduction and data analysis.

**PCA conceptual overview.** Find directions of maximum variance in data;
these are the principal components — eigenvectors of the covariance matrix.

**Covariance matrix calculation.** C = (1/(n−1))XᵀX for centered data
matrix X (columns have mean 0).

**Variance maximization view.** The first principal component maximizes
variance of projected data: maxᵢᵀᵢ=1 xᵀCx → top eigenvector of C.

**Dimensionality reduction steps.** Center data, compute C, take top-k
eigenvectors as projection matrix, project: Z = XQₖ.

**Data projection via SVD.** X = UΣVᵀ; principal components are columns of
V; scores are UΣ (or XV).

**Principal components interpretation.** PC₁ is the direction of greatest
variance; PC₂ is the greatest-variance direction orthogonal to PC₁, etc.

**Noise filtering applications.** Keep only large-singular-value components
to denoise; discard small σᵢ associated with noise.

**Worked example.** Data X = [[−1, −1], [1, 1]] (centered). C = XᵀX =
[[2, 2], [2, 2]] → eigenvalues 4, 0 → PC₁ = (1, 1)/√2 with variance 4,
PC₂ = (1, −1)/√2 with variance 0 (all variance along the line y = x).

**Exercises.**
1. Center X = [[1, 2], [3, 4]] and compute its covariance matrix.
2. Find principal components of C = [[2, 2], [2, 2]].
3. Project the data of exercise 1 onto its first principal component.

---

## References

"Numerical Linear Algebra" (Trefethen & Bau) for LU, Cholesky, QR, SVD;
MIT OpenCourseWare 18.06 lectures by Gilbert Strang; Khan Academy Linear
Algebra; "Pattern Recognition and Machine Learning" (Bishop) for PCA;
"Matrix Analysis" (Horn & Johnson). Entries: LU decomposition, Cholesky,
spectral theorem, singular value decomposition, principal component analysis
on Wikipedia and MathWorld.
