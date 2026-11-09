# Eigenvalues and Eigenvectors

## Abstract

This article develops eigenvalues, eigenvectors, characteristic polynomials,
diagonalization, complex spectra, and quadratic forms. Every section states
the definition, the principal identities, a worked example, and an exercise.
The article covers the full S05 module checklist of 35 concepts across 5
subtopics.

**Keywords:** eigenvalue, eigenvector, characteristic polynomial, spectrum,
eigenspace, algebraic multiplicity, geometric multiplicity, diagonalization,
similarity, complex eigenvalue, Jordan form, quadratic form, positive
definite, Sylvester criterion.

---

## 1. Eigenvalue Fundamentals

An eigenvector of a square matrix A is a nonzero vector v with Av = λv for
some scalar λ; λ is then called an eigenvalue of A.

**Eigenvalue eigenvector equation.** Av = λv with v ≠ 0; λ is the
eigenvalue associated with eigenvector v.

**Characteristic polynomial derivation.** det(A − λI) = 0 is the
characteristic equation; p(λ) = det(λI − A) is the characteristic polynomial
(monic, degree n).

**Trace and determinant connection.** tr(A) = Σᵢ λᵢ (sum of eigenvalues,
counted with algebraic multiplicity); det(A) = Πᵢ λᵢ.

**Spectrum of a matrix.** The spectrum σ(A) is the set of all eigenvalues
of A.

**Eigenspace definition.** E_λ = {v : Av = λv} ∪ {0} is the eigenspace of
λ — the null space of (A − λI), a subspace.

**Geometric multiplicity.** dim(E_λ), the dimension of the eigenspace of
λ.

**Algebraic multiplicity.** The multiplicity of λ as a root of the
characteristic polynomial. Geometric multiplicity ≤ algebraic multiplicity.

**Worked example.** A = [[3, 1], [0, 2]]. p(λ) = (3−λ)(2−λ) → λ = 3, 2.
For λ = 3: (A − 3I)v = 0 → [0 1; 0 −1]v = 0 → v = (1, 0). For λ = 2:
[1 1; 0 0]v = 0 → v = (1, −1).

**Exercises.**
1. Find eigenvalues and eigenvectors of [[2, 0], [0, 3]].
2. Verify tr(A) = Σλᵢ and det(A) = Πλᵢ for A = [[3, 1], [0, 2]].
3. Find the eigenspace of λ = 1 for A = [[1, 1], [0, 1]].

---

## 2. Characteristic Equation

The characteristic equation det(A − λI) = 0 determines all eigenvalues and
their algebraic multiplicities.

**Setting up characteristic equation.** Compute det(λI − A) (or det(A −
λI)) and set equal to 0.

**Finding roots of polynomial.** Solve p(λ) = 0 for its roots — these are
the eigenvalues, possibly repeated or complex.

**Cayley-Hamilton theorem.** Every square matrix satisfies its own
characteristic equation: p(A) = 0 (the zero matrix).

**Invariant subspaces.** A subspace W is A-invariant if A(W) ⊆ W; eigenspaces
are invariant subspaces.

**Spectral radius definition.** ρ(A) = max{|λ| : λ ∈ σ(A)}, the largest
absolute eigenvalue.

**Gershgorin circle theorem.** Every eigenvalue lies in some Gershgorin
disc Dᵢ = {z : |z − aᵢᵢ| ≤ Σⱼ≠ᵢ |aᵢⱼ|} centered at a diagonal entry.

**Schur triangulation theorem.** Every complex square matrix is unitarily
similar to an upper triangular matrix whose diagonal entries are its
eigenvalues.

**Worked example.** A = [[4, 1], [2, 3]]: p(λ) = (4−λ)(3−λ) − 2 = λ² − 7λ
+ 10 = (λ−2)(λ−5) → λ = 2, 5. Check Cayley-Hamilton: A² − 7A + 10I = 0.

**Exercises.**
1. Find the characteristic polynomial of [[1, 2], [3, 4]].
2. Find eigenvalues of [[0, −1], [1, 0]].
3. Verify Cayley-Hamilton for A = [[2, 0], [0, 3]].

---

## 3. Diagonalization

A matrix is diagonalizable when it is similar to a diagonal matrix —
equivalently, when it has a full set of n linearly independent eigenvectors.

**Diagonalizable matrix definition.** A = PDP⁻¹ for some invertible P and
diagonal D.

**Condition for diagonalizability.** A is diagonalizable iff the sum of
geometric multiplicities equals n, equivalently A has n linearly
independent eigenvectors.

**Diagonalization formula.** A = PDP⁻¹ where columns of P are eigenvectors
and D = diag(λ₁, …, λₙ) holds the corresponding eigenvalues.

**Similarity transformation.** B = P⁻¹AP is similar to A; similar matrices
share eigenvalues, trace, determinant, rank.

**Computing matrix powers.** Aᵏ = PDᵏP⁻¹ — powers are easy once diagonalized.

**Matrix exponential calculation.** eᴬ = P eᴰ P⁻¹ where eᴰ =
diag(e^{λ₁}, …, e^{λₙ}).

**Simultaneous diagonalization.** Commuting diagonalizable matrices can be
diagonalized by the same P (e.g. symmetric matrices sharing eigenvectors).

**Worked example.** A = [[3, 1], [0, 2]] with P = [[1, 1], [0, −1]],
D = [[3, 0], [0, 2]]. Then A = PDP⁻¹ and Aᵏ = PDᵏP⁻¹.

**Exercises.**
1. Diagonalize [[2, 0], [0, 3]] (already diagonal).
2. Is [[1, 1], [0, 1]] diagonalizable?
3. Compute A³ for A = [[3, 1], [0, 2]] via diagonalization.

---

## 4. Complex Eigenvalues

Real matrices may have complex eigenvalues and eigenvectors, occurring in
conjugate pairs, corresponding to rotation-scaling behavior.

**Complex number review.** z = a + bi, i² = −1; conjugate z̄ = a − bi;
modulus |z| = √(a² + b²).

**Complex eigenvalues occurrence.** Real matrices have real coefficients in
p(λ), so non-real roots occur in conjugate pairs λ, λ̄.

**Complex eigenvectors calculation.** Solve (A − λI)v = 0 over ℂ; the
eigenvector for λ̄ is the conjugate of that for λ.

**Rotation scaling representation.** A 2×2 real matrix with complex
eigenvalues a ± bi acts as a rotation by θ and scaling by r = √(a²+b²).

**Real canonical forms.** A real block-diagonal form with 2×2 blocks [[a,
−b], [b, a]] for complex pairs and real eigenvalues on the diagonal.

**Jordan canonical form introduction.** Every complex matrix is similar to a
Jordan form — diagonal blocks with eigenvalues on the diagonal and 1s on
the superdiagonal for defective eigenvalues.

**Spectral theorem for real matrices.** A real symmetric matrix is
orthogonally diagonalizable with real eigenvalues.

**Worked example.** A = [[0, −1], [1, 0]] (rotation by 90°): p(λ) = λ² + 1
→ λ = ±i. For λ = i: (A − iI)v = 0 → v = (1, −i) up to scale.

**Exercises.**
1. Find complex eigenvalues of [[0, −1], [1, 0]].
2. Show eigenvalues of a real matrix occur in conjugate pairs.
3. Write the real canonical form of [[0, −1], [1, 0]].

---

## 5. Quadratic Forms

A quadratic form Q(x) = xᵀAx with symmetric A classifies as positive
definite, negative definite, indefinite, or semidefinite.

**Quadratic form definition.** Q(x) = xᵀAx; only the symmetric part of A
matters since xᵀAx = xᵀ((A + Aᵀ)/2)x.

**Symmetric matrix association.** Every quadratic form is represented by a
unique symmetric matrix A = (A + Aᵀ)/2.

**Positive definite matrices.** Q(x) > 0 for all x ≠ 0; equivalently all
eigenvalues > 0 or all leading principal minors > 0.

**Negative definite matrices.** Q(x) < 0 for all x ≠ 0; all eigenvalues < 0.

**Indefinite matrices.** Q takes both positive and negative values;
eigenvalues of mixed sign.

**Principal axis theorem.** A real symmetric matrix is orthogonally
diagonalizable: Q = λ₁y₁² + … + λₙyₙ² in principal-axis coordinates.

**Sylvester criterion.** A is positive definite iff all leading principal
minors are positive.

**Worked example.** Q(x, y) = x² + 4xy + y² = [x y][[1, 2], [2, 1]][x; y].
Eigenvalues of [[1, 2], [2, 1]] are 3, −1 → indefinite (mixed signs).

**Exercises.**
1. Classify Q(x) = x₁² + x₂² (matrix [[1, 0], [0, 1]]).
2. Use Sylvester's criterion on [[2, 1], [1, 2]].
3. Diagonalize Q(x, y) = x² + 4xy + y² by principal axes.

---

## References

Khan Academy Linear Algebra (eigenvalues, eigenvectors, diagonalization);
MIT OpenCourseWare 18.06 lectures by Gilbert Strang; 3Blue1Brown linear
algebra series; "Linear Algebra and Its Applications" (Lay); "Matrix
Analysis" (Horn & Johnson). Entries: eigenvalue, eigenvector, characteristic
polynomial, diagonalization, Jordan form, quadratic form, positive definite,
spectral theorem on Wikipedia and MathWorld.
