# Linear Transformations

## Abstract

This article develops linear transformations between vector spaces: their
axioms, kernel and range, matrix representation, composition, geometric
examples in the plane, and orthogonal transformations. Every section states
the definition, the principal identities, a worked example, and an exercise.
The article covers the full S06 module checklist of 28 concepts across 4
subtopics.

**Keywords:** linear transformation, kernel, range, rank-nullity theorem,
standard matrix, composition, inverse transformation, scaling, rotation,
reflection, shear, projection, orthogonal operator, rigid motion.

---

## 1. Transformation Fundamentals

A linear transformation T: V → W between vector spaces preserves addition
and scalar multiplication: T(u + v) = T(u) + T(v) and T(cu) = cT(u).

**Function mapping definition.** A function T maps each element of V to an
element of W; written T: V → W, T(v) = w.

**Linear transformation axioms.** T(u + v) = T(u) + T(v) and T(cu) = cT(u)
for all u, v ∈ V and scalars c. Equivalently T(c₁u₁ + … + cₖuₖ) =
c₁T(u₁) + … + cₖT(uₖ).

**Kernel of transformation.** ker(T) = {v ∈ V : T(v) = 0}, a subspace of V
(the null space of its matrix).

**Range of transformation.** range(T) = {T(v) : v ∈ V}, a subspace of W
(the column space of its matrix).

**Rank-nullity theorem proof.** dim V = dim ker(T) + dim range(T). Proof:
extend a basis of ker(T) to a basis of V; the images of the added vectors
form a basis of range(T).

**One-to-one transformations.** T is one-to-one (injective) iff ker(T) = {0}.

**Onto transformations.** T is onto (surjective) iff range(T) = W.

**Worked example.** T: R² → R², T(x, y) = (x + y, x − y). Linear since
T(c(x,y) + (x',y')) = cT(x,y) + T(x',y'). ker(T): x + y = 0, x − y = 0 →
(0, 0), so one-to-one. range(T) = R² since any (a, b) = T((a+b)/2,
(a−b)/2), so onto.

**Exercises.**
1. Show T(x, y) = (2x, 3y) is linear.
2. Find ker(T) and range(T) for T(x, y) = (x + y, 0).
3. Is T(x) = x + b (translation) linear? Explain.

---

## 2. Matrix Representation

Every linear transformation T: Rⁿ → Rᵐ is given by a matrix A with T(x) =
Ax; conversely every matrix defines a linear transformation.

**Standard matrix of transformation.** The matrix A whose j-th column is
T(eⱼ), where eⱼ are standard basis vectors; then T(x) = Ax.

**Transformation of basis.** Knowing T on a basis determines T on the whole
space: T(Σcᵢvᵢ) = ΣcᵢT(vᵢ).

**Composition of transformations.** (S ∘ T)(x) = S(T(x)); matrix of S ∘ T
is the product of matrices of S and T.

**Inverse transformations.** T is invertible iff its matrix A is
invertible; T⁻¹(x) = A⁻¹x.

**Change of basis for operators.** If A is the matrix of T in basis B, then
in basis B′ the matrix is A′ = P⁻¹AP where P is the change-of-basis matrix.

**Similarity of matrices.** A′ = P⁻¹AP means A and A′ are similar; they
represent the same transformation in different bases.

**Coordinate isomorphism.** The map v ↦ [v]_B from V to Rⁿ (coordinates in
basis B) is a linear isomorphism.

**Worked example.** T(x, y) = (x + y, x − y). Standard basis: T(1, 0) =
(1, 1), T(0, 1) = (1, −1), so A = [[1, 1], [1, −1]]. T(x) = Ax.

**Exercises.**
1. Find the standard matrix of T(x, y) = (2x + y, x − 3y).
2. Find the matrix of S ∘ T for S(x) = 2x, T(x, y) = (x + y, x − y).
3. Show T is invertible iff its standard matrix is invertible.

---

## 3. Geometric Transformations

Linear maps R² → R² include scaling, rotation, reflection, shear, and
projection; translations require the affine extension.

**Scaling transformations in plane.** S(x, y) = (ax, by) scales x by a and
y by b; matrix [[a, 0], [0, b]].

**Rotation transformations in plane.** R_θ(x, y) = (x cosθ − y sinθ,
x sinθ + y cosθ); matrix [[cosθ, −sinθ], [sinθ, cosθ]].

**Reflection transformations in plane.** Reflection across a line through
the origin; e.g. across x-axis: [[1, 0], [0, −1]].

**Shear transformations in plane.** H(x, y) = (x + ky, y) shears parallel
to the x-axis; matrix [[1, k], [0, 1]].

**Translation affine extension.** Translation is not linear (does not fix
the origin); represented affinely as x ↦ x + b or via homogeneous
coordinates.

**Projection transformations.** Projection onto a line spanned by u:
proj_u(x) = ((x·u)/(u·u))u; matrix (uuᵀ)/(uᵀu).

**Composition of geometric operations.** Composition of rotations is a
rotation; composition of reflections can be a rotation or reflection.

**Worked example.** Rotate (1, 0) by 90°: R_90 = [[0, −1], [1, 0]] →
(0, 1). Reflect (1, 2) across x-axis: (1, −2). Shear (1, 2) by k = 1: (3,
2).

**Exercises.**
1. Write the matrix for rotation by 180° in R².
2. Find the matrix for projection onto the x-axis.
3. Compose: reflect across x-axis then rotate by 90°; give the matrix.

---

## 4. Orthogonal Transformations

Orthogonal transformations preserve inner products, lengths, and angles;
their matrices satisfy QᵀQ = I.

**Orthogonal operator definition.** T is orthogonal if ⟨T(u), T(v)⟩ =
⟨u, v⟩ for all u, v; equivalently its matrix Q satisfies QᵀQ = I.

**Preservation of inner product.** Orthogonal transformations preserve
dot products, hence lengths and angles.

**Length preservation property.** ‖T(v)‖ = ‖v‖ for all v.

**Orthogonal matrix representation.** Q is orthogonal iff its columns form
an orthonormal set; Q⁻¹ = Qᵀ; det(Q) = ±1.

**Reflection across subspace.** Reflection across a subspace W: fixes W and
negates W⊥; matrix Q = I − 2P_{W⊥} style formulas.

**Rotation in higher dimensions.** Givens rotations rotate a coordinate
plane while fixing the orthogonal complement.

**Rigid body motions.** Composition of an orthogonal transformation and a
translation: x ↦ Qx + b — preserves all distances.

**Worked example.** Q = [[0, −1], [1, 0]] is orthogonal: QᵀQ = I, det(Q) =
1, it rotates by 90° preserving all lengths.

**Exercises.**
1. Show Q = [[cosθ, −sinθ], [sinθ, cosθ]] is orthogonal.
2. Show that orthogonal matrices preserve lengths: ‖Qx‖ = ‖x‖.
3. Is [[1, 1], [0, 1]] orthogonal? Explain.

---

## References

Khan Academy Linear Algebra (linear transformations); MIT OpenCourseWare
18.06 lectures by Gilbert Strang; 3Blue1Brown linear algebra series;
"Linear Algebra and Its Applications" (Lay); "Introduction to Linear Algebra"
(Strang). Entries: linear transformation, kernel, range, rank-nullity
theorem, orthogonal matrix, rotation matrix, projection on Wikipedia and
MathWorld.
