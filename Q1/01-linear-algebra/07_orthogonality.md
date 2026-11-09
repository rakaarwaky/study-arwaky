# Orthogonality

## Abstract

This article develops orthogonal and orthonormal sets, Gram-Schmidt
orthogonalization, QR decomposition, orthogonal projections, least squares,
and applications to pseudoinverses. Every section states the definition, the
principal identities, a worked example, and an exercise. The article covers
the full S07 module checklist of 28 concepts across 4 subtopics.

**Keywords:** orthogonal set, orthonormal set, Parseval identity, Bessel
inequality, Gram-Schmidt, QR decomposition, Householder reflection, Givens
rotation, orthogonal projection, least squares, normal equations, pseudoinverse.

---

## 1. Orthogonal Sets

An orthogonal set is a collection of mutually perpendicular nonzero vectors;
an orthonormal set additionally has unit-length vectors.

**Orthogonal vector sets.** A set {u₁, …, uₖ} is orthogonal when
⟨uᵢ, uⱼ⟩ = 0 for all i ≠ j and all vectors are nonzero.

**Orthonormal vector sets.** An orthonormal set satisfies ⟨uᵢ, uⱼ⟩ = δᵢⱼ:
mutually perpendicular and each of length 1.

**Linear independence of orthogonal sets.** Every orthogonal set of nonzero
vectors is linearly independent: if Σcᵢuᵢ = 0 then taking inner product
with uⱼ gives cⱼ‖uⱼ‖² = 0, so cⱼ = 0.

**Coordinate extraction formula.** For an orthonormal basis {e₁, …, eₙ},
the coordinates of v are cᵢ = ⟨v, eᵢ⟩.

**Parseval identity.** For an orthonormal basis, ‖v‖² = Σᵢ |⟨v, eᵢ⟩|².

**Bessel inequality.** For any orthonormal set {e₁, …, eₖ}, ‖v‖² ≥
Σᵢ₌₁ᵏ |⟨v, eᵢ⟩|².

**Orthogonal projection formula.** proj_W(v) = Σᵢ₌₁ᵏ ⟨v, eᵢ⟩eᵢ for an
orthonormal basis {e₁, …, eₖ} of W.

**Worked example.** {(1, 1, 0), (1, −1, 0)} is orthogonal. Normalize:
{(1/√2, 1/√2, 0), (1/√2, −1/√2, 0)} is orthonormal. Coordinates of
(3, 1, 0) are ⟨(3,1,0), e₁⟩ = 4/√2 = 2√2, ⟨(3,1,0), e₂⟩ = 2/√2 = √2.

**Exercises.**
1. Show {(1, 0), (0, 1)} is orthonormal.
2. Show {(1, 1), (1, −1)} is orthogonal but not orthonormal; normalize it.
3. Verify Parseval for v = (3, 4) in the standard basis of R².

---

## 2. Gram-Schmidt Process

Gram-Schmidt converts a linearly independent set into an orthonormal set
spanning the same subspace, one vector at a time.

**Orthogonalization algorithm steps.** u₁ = v₁; uₖ = vₖ − Σⱼ<ₖ ⟨vₖ, eⱼ⟩eⱼ
where eⱼ = uⱼ/‖uⱼ‖; repeat for k = 2, …, n.

**Normalization step.** eₖ = uₖ/‖uₖ‖ after each orthogonalization.

**QR decomposition introduction.** Gram-Schmidt on the columns of A yields
A = QR with Q having orthonormal columns and R upper triangular.

**Modified Gram-Schmidt method.** Orthogonalize against each eⱼ
sequentially and update the remaining vector — more numerically stable.

**Numerical stability issues.** Classical Gram-Schmidt can lose orthogonality
in floating point; modified Gram-Schmidt or Householder reflections are
preferred numerically.

**Householder reflections method.** Reflect vectors across hyperplanes to
zero out entries below the diagonal — the standard stable QR algorithm.

**Givens rotations method.** Rotate coordinate planes to zero entries one at
a time — useful for sparse matrices and parallel implementation.

**Worked example.** Orthonormalize {(1, 1), (1, 0)}. u₁ = (1, 1),
e₁ = (1/√2, 1/√2). u₂ = (1, 0) − ⟨(1,0), e₁⟩e₁ = (1,0) − (1/√2)(1/√2,
1/√2) = (1/2, −1/2). e₂ = (1/√2, −1/√2).

**Exercises.**
1. Apply Gram-Schmidt to {(1, 1), (1, 0)}.
2. Apply Gram-Schmidt to {(1, 2, 2), (2, 1, −2)}.
3. Show that Gram-Schmidt output spans the same subspace as the input.

---

## 3. Orthogonal Projections

Projection decomposes a vector into a part in a subspace and a part
orthogonal to it, enabling least squares.

**Projection onto subspace.** proj_W(v) is the unique w ∈ W with v − w ∈
W⊥; it is the closest point in W to v.

**Projection matrix construction.** For orthonormal basis Q of W, the
projection matrix is P = QQᵀ; proj_W(v) = QQᵀv.

**Orthogonal decomposition theorem.** v = proj_W(v) + (v − proj_W(v)) with
the two parts orthogonal; ‖v‖² = ‖proj_W(v)‖² + ‖v − proj_W(v)‖².

**Distance from point to subspace.** dist(v, W) = ‖v − proj_W(v)‖.

**Least squares approximation.** For inconsistent Ax = b, the least-squares
solution minimizes ‖Ax − b‖ and satisfies the normal equations AᵀAx =
Aᵀb.

**Normal equations derivation.** Aᵀ(Ax − b) = 0 → AᵀAx = Aᵀb; the solution
is the projection of b onto the column space of A.

**Pseudoinverse calculation.** A⁺ = (AᵀA)⁻¹Aᵀ when A has full column rank;
the least-squares solution is x̂ = A⁺b.

**Worked example.** Project b = (3, 4, 5) onto W = span{(1, 1, 1)}.
proj_W(b) = (b·u/(u·u))u with u = (1,1,1): b·u = 12, u·u = 3 → proj = 4(1,1,1) = (4,4,4). Distance = ‖(−1, 0, 1)‖ = √2.

**Exercises.**
1. Project (3, 4) onto span{(1, 0)}.
2. Find the projection matrix onto span{(1, 1)} in R².
3. Solve least squares for A = [[1, 1], [1, 2], [1, 3]], b = [1, 2, 2].

---

## 4. QR Decomposition

QR factors a matrix into an orthonormal matrix Q and an upper triangular R,
the foundation of many numerical algorithms.

**QR factorization definition.** A = QR where Q has orthonormal columns
and R is upper triangular; exists for any matrix with linearly independent
columns.

**Gram-Schmidt based QR.** Q from Gram-Schmidt on columns of A; Rᵢⱼ =
⟨aⱼ, qᵢ⟩ (entries of R are the projection coefficients).

**Householder triangularization.** Apply Householder reflections to zero
entries below the diagonal, accumulating Q as the product of reflections.

**Solving systems using QR.** Ax = b → QRx = b → Rx = Qᵀb → back substitution
since R is triangular.

**Least squares via QR.** x̂ = R⁻¹Qᵀb minimizes ‖Ax − b‖ when A has full
column rank.

**Eigenvalue computation via QR.** The QR algorithm iterates Aₖ = QₖRₖ,
Aₖ₊₁ = RₖQₖ; Aₖ converges to Schur form, revealing eigenvalues.

**Uniqueness of QR decomposition.** QR is unique when R has positive
diagonal entries (for full-column-rank A).

**Worked example.** A = [[1, 1], [1, 0]]. q₁ = (1/√2, 1/√2), r₁₁ = √2,
r₁₂ = 1/√2. u₂ = (1, 0) − (1/√2)q₁ = (1/2, −1/2), q₂ = (1/√2, −1/√2),
r₂₂ = 1/√2. Q = [[1/√2, 1/√2], [1/√2, −1/√2]], R = [[√2, 1/√2], [0,
1/√2]].

**Exercises.**
1. Find QR of [[1, 1], [1, 0]] via Gram-Schmidt.
2. Solve [[1, 1], [1, 0]]x = [2, 1] using QR.
3. Show R is unique when its diagonal is positive.

---

## References

Khan Academy Linear Algebra (orthogonality, projections); MIT OpenCourseWare
18.06 lectures by Gilbert Strang (orthogonal matrices, Gram-Schmidt, QR,
least squares); 3Blue1Brown linear algebra series; "Numerical Linear
Algebra" (Trefethen & Bau) for Householder and Givens; "Linear Algebra and
Its Applications" (Lay). Entries: orthogonal projection, Gram-Schmidt, QR
decomposition, least squares, pseudoinverse, Householder reflection on
Wikipedia and MathWorld.
