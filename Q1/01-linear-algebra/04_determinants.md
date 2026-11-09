# Determinants

## Abstract

This article develops the determinant of a square matrix: its geometric
meaning, computational formulas, algebraic properties, cofactor expansion,
and geometric applications. Every section states the definition, the
principal identities, a worked example, and an exercise. The article covers
the full S04 module checklist of 28 concepts across 4 subtopics.

**Keywords:** determinant, minor, cofactor, expansion by minors, adjoint,
Cramer's rule, triangular matrix, row operations, parallelogram area,
parallelepiped volume, Jacobian, orientation.

---

## 1. Determinant Fundamentals

The determinant is a scalar function of a square matrix that measures how
the associated linear transformation scales volumes and reverses or
preserves orientation.

**Determinant geometric meaning.** det(A) is the signed factor by which the
linear map x ↦ Ax scales n-dimensional volumes; its sign indicates whether
orientation is preserved.

**Determinant of scalar.** det(cA) = cⁿ det(A) for an n×n matrix A and
scalar c — scaling every row by c scales the determinant by cⁿ.

**Two by two determinant.** det[[a, b], [c, d]] = ad − bc.

**Three by three determinant.** det[[a, b, c], [d, e, f], [g, h, i]] =
a(ei − fh) − b(di − fg) + c(dh − eg).

**Expansion by minors.** det(A) = Σⱼ (−1)ⁱ⁺ʲ aᵢⱼ Mᵢⱼ where Mᵢⱼ is the
determinant of the submatrix deleting row i and column j.

**Cofactor expansion method.** det(A) = Σⱼ aᵢⱼ Cᵢⱼ along any row i, or
Σᵢ aᵢⱼ Cᵢⱼ along any column j, where Cᵢⱼ = (−1)ⁱ⁺ʲMᵢⱼ.

**Sign pattern chessboard.** Cofactor signs follow the checkerboard pattern
+ − + − … / − + − + …, i.e. sign (−1)ⁱ⁺ʲ at position (i, j).

**Worked example.** det[[1, 2], [3, 4]] = 1·4 − 2·3 = −2. det[[1, 2, 3],
[4, 5, 6], [7, 8, 10]] = 1(50−48) − 2(40−42) + 3(32−35) = 2 + 4 − 9 = −3.

**Exercises.**
1. Compute det[[2, 3], [5, 7]].
2. Compute det[[1, 0, 2], [0, 1, 3], [4, 5, 6]].
3. Verify det(cA) = cⁿdet(A) for A = [[1, 2], [3, 4]], c = 2, n = 2.

---

## 2. Properties of Determinants

Determinants behave predictably under row operations and matrix products,
which makes them computationally useful and theoretically rich.

**Determinant of transpose.** det(Aᵀ) = det(A).

**Determinant of product.** det(AB) = det(A)det(B) for square matrices of
the same size.

**Effect of row swapping.** Swapping two rows multiplies the determinant by
−1.

**Effect of scaling a row.** Multiplying one row by c multiplies the
determinant by c.

**Effect of adding row multiples.** Adding a multiple of one row to another
leaves the determinant unchanged.

**Determinant of inverse matrix.** det(A⁻¹) = 1 / det(A) when A is
invertible.

**Determinant of triangular matrix.** The determinant of a triangular
matrix is the product of its diagonal entries.

**Worked example.** A = [[1, 2, 3], [0, 4, 5], [0, 0, 6]] is upper
triangular, so det(A) = 1·4·6 = 24. Swapping rows 1 and 2 of [[1, 2],
[3, 4]] changes det from −2 to 2.

**Exercises.**
1. Show det(Aᵀ) = det(A) for A = [[1, 2], [3, 4]].
2. If det(A) = 3 and det(B) = −2, find det(AB), det(A⁻¹), det(2A) for
   2×2 matrices.
3. Row-swap [[1, 2, 3], [4, 5, 6]] twice and track the determinant sign.

---

## 3. Cofactor Expansion

Cofactor expansion computes the determinant recursively along any row or
column, and underlies the adjoint matrix and Cramer's rule.

**Minor matrix definition.** Mᵢⱼ is the (n−1)×(n−1) matrix obtained by
deleting row i and column j of A.

**Cofactor definition and signs.** Cᵢⱼ = (−1)ⁱ⁺ʲ det(Mᵢⱼ), the signed
minor.

**Expansion along any row.** det(A) = Σⱼ₌₁ⁿ aᵢⱼCᵢⱼ for any fixed row i.

**Expansion along any column.** det(A) = Σᵢ₌₁ⁿ aᵢⱼCᵢⱼ for any fixed column
j.

**Adjoint matrix definition.** adj(A) is the transpose of the cofactor
matrix: adj(A)ᵢⱼ = Cⱼᵢ.

**Inverse via adjoint matrix.** A⁻¹ = adj(A) / det(A) when det(A) ≠ 0.

**Cramer's rule derivation.** xᵢ = det(Aᵢ(b)) / det(A) follows from
expanding det(Aᵢ(b)) along column i after replacing it with b.

**Worked example.** det[[1, 2, 3], [0, 4, 5], [1, 0, 6]] expand along row 2:
−4·det[[1, 3], [1, 6]] + 5·det[[1, 2], [1, 0]] = −4(6−3) + 5(0−2) = −12 −
10 = −22 (sign pattern for row 2: − + −).

**Exercises.**
1. Compute det[[1, 2, 3], [4, 5, 6], [7, 8, 10]] by cofactor expansion
   along row 1.
2. Find adj(A) and A⁻¹ for A = [[1, 2], [3, 4]].
3. Solve x + y = 3, 2x − y = 0 via Cramer's rule.

---

## 4. Geometric Applications

Determinants encode oriented area, volume, and scaling under linear maps.

**Area of parallelogram in plane.** |det[u v]| where u, v are column vectors
in R² is the area of the parallelogram they span.

**Volume of parallelepiped in space.** |det[u v w]| for u, v, w ∈ R³ is
the volume of the parallelepiped they span.

**Orientation of coordinate systems.** sign(det) indicates whether a basis
has the same (+) or opposite (−) orientation as the standard basis.

**Linear transformation scaling factor.** det(A) is the factor by which the
map x ↦ Ax scales all n-dimensional volumes.

**Jacobian determinant introduction.** For a differentiable map F: Rⁿ →
Rⁿ, det(JF) gives the local volume scaling factor used in change of
variables for integrals.

**Determinant zero meaning.** det(A) = 0 exactly when A is singular
(non-invertible), exactly when its columns are linearly dependent, exactly
when the map x ↦ Ax collapses volume to zero.

**Cross product via determinant.** u × v = |i j k; u₁ u₂ u₃; v₁ v₂ v₃|,
computed as a determinant with basis vectors in the first row.

**Worked example.** u = (1, 0), v = (0, 1) span the unit square: |det[[1,
0], [0, 1]]| = 1. u = (2, 0), v = (0, 3) span a rectangle of area |det[[2,
0], [0, 3]]| = 6. A = [[1, 2], [2, 4]] has det = 0: columns are dependent,
the map collapses R² to a line.

**Exercises.**
1. Find the area of the parallelogram spanned by (1, 2) and (3, −1).
2. Find the volume of the parallelepiped spanned by (1,0,0), (0,2,0),
   (0,0,3).
3. Show det[[1, 2], [2, 4]] = 0 and describe the image of the map.

---

## References

Khan Academy Linear Algebra (determinants); MIT OpenCourseWare 18.06
lectures by Gilbert Strang; "Linear Algebra and Its Applications" (Lay);
"Introduction to Linear Algebra" (Strang). Entries: determinant, cofactor,
adjoint matrix, Cramer's rule, Jacobian on Wikipedia and MathWorld.
