# Vectors and Their Spaces

## Abstract

This article develops the core objects of introductory linear algebra and the operations that connect them. It proceeds from the geometric and algebraic representation of vectors, through the dot and cross products, to the axiomatic structure of vector spaces with subspaces, linear independence, span, basis, and dimension. The four fundamental subspaces of a matrix are treated through rank and nullity. Inner product spaces supply length, angle, and the Cauchy–Schwarz and triangle inequalities, and orthonormal bases are constructed by Gram–Schmidt orthogonalization. The final section addresses coordinate systems, change of basis, vector-space isomorphisms, the dual space, linear functionals, and annihilator subspaces. Every section states the definition, the principal identities, a proof or worked example, and an exercise. The article covers the full S01 module checklist of 49 concepts across 7 subtopics and consolidates the reference list attached to that module.

**Keywords:** vector, dot product, cross product, vector space, subspace, linear independence, span, basis, dimension, fundamental subspaces, rank, nullity, inner product, orthonormal basis, Gram–Schmidt, change of basis, isomorphism, dual space, linear functional, annihilator.

---

## 1. Vector Fundamentals

A vector is an object with magnitude and direction. Geometrically it is drawn as an arrow from an initial point A to a terminal point B; the word is Latin for "carrier." Algebraically, a vector in Rⁿ is a column of components (v₁, …, vₙ), and the two representations agree because addition and scalar multiplication act componentwise. This section fixes the seven elementary operations that make Rⁿ a vector space.

**Geometric vector representation.** Two vectors are equal when they share magnitude and direction, regardless of position. The additive inverse of A is the vector of equal length in the opposite direction, written −A. The zero vector has magnitude 0 and undefined direction, and a unit vector has length 1 and indicates a direction. A localized vector is named by its initial and terminal points, OP, while a free vector carries no fixed position.

**Algebraic vector representation.** A vector in Rⁿ is a list (v₁, …, vₙ). Common notations are bold capitals (F) and an arrow over the symbol (v⃗). In R³ the standard basis is i = (1, 0, 0), j = (0, 1, 0), k = (0, 0, 1), and any vector writes as aî + bĵ + c k̂.

**Vector addition operations.** Addition is commutative and associative, and is represented geometrically by the parallelogram or triangle rule. Componentwise, if a = (a₁, a₂, a₃) and b = (b₁, b₂, b₃), then a + b = (a₁+b₁, a₂+b₂, a₃+b₃). Subtraction is addition of the opposite: a − b = a + (−b).

**Scalar multiplication rules.** A scalar multiple c·a scales the vector's length by |c|; a negative scalar reverses its direction. The rules are (c + d)·a = c·a + d·a, c·(a + b) = c·a + c·b, and (cd)·a = c·(d·a), with 1·a = a. Componentwise, c·a = (ca₁, ca₂, ca₃).

**Vector magnitude calculation.** The magnitude (or length, or norm) of a = (a₁, a₂, a₃) is |a| = √(a₁² + a₂² + a₃²), the Euclidean distance from the origin. In Rⁿ, |a| = √(Σ aᵢ²). This is the length of the position vector, so it depends only on the components, not on any particular location.

**Unit vector normalization.** The unit vector in the direction of a nonzero vector a is â = a / |a|. It has length 1 and the same direction as a. The standard basis vectors are the simplest unit vectors: i, j, k. Any nonzero vector decomposes as a = |a| â, a scalar times its own direction.

**Position vectors in space.** The position vector of P(a, b, c) is OP = aî + bĵ + c k̂, the vector from the origin to P. The vector from P(a₁, b₁, c₁) to Q(a₂, b₂, c₂) is PQ = (a₂−a₁, b₂−b₁, c₂−c₁). Two localized vectors are equivalent when their components agree, since magnitude and direction then agree.

**Direction cosines.** The direction cosines of a nonzero vector a = (a₁, a₂, a₃) are l = a₁/|a|, m = a₂/|a|, n = a₃/|a|, the cosines of the angles the vector makes with the x, y, z axes. Because the unit vector has length 1, they satisfy l² + m² + n² = 1.

**Worked example.** Let a = (3, 4). Then |a| = √(9+16) = 5, â = (3/5, 4/5), and the direction cosines in the plane are (3/5, 4/5). The position vector of P(−1, 2) is (−1, 2), and the vector from P to Q(1, 0) is (2, −2).

**Exercises.**
1. For a = (1, 2, 2), find |a|, â, and its direction cosines.
2. Given P(2, −1) and Q(5, 3), find PQ, its magnitude, and its unit direction.

**Concept summary.**

| Concept | Geometric reading | Algebraic formula (R³) |
|---|---|---|
| Vector | An object with magnitude and direction, drawn as an arrow. | An ordered triple (v₁, v₂, v₃), usually a column. |
| Vector addition | Parallelogram or triangle rule. | Componentwise: a + b = (a₁+b₁, a₂+b₂, a₃+b₃). |
| Scalar multiplication | Scale the arrow by c; reverse it if c < 0. | c·a = (ca₁, ca₂, ca₃). |
| Magnitude | Length of the arrow. | a = √(a₁² + a₂² + a₃²). |
| Unit vector | Arrow of length 1 in the same direction. | â = a / a. |
| Direction cosines | Cosines of the angles with the x, y, z axes. | l = a₁/a, m = a₂/a, n = a₃/a, with l² + m² + n² = 1. |

---

## 2. Vector Dot Product

The dot (scalar) product of two vectors returns a scalar. It measures how much two vectors point in the same direction and underlies the definitions of angle, orthogonality, projection, and the key inequalities of Euclidean geometry.

**Geometric dot product definition.** a·b = |a||b| cos θ, where θ is the angle between a and b. The product is largest when the vectors are parallel and zero when they are perpendicular.

**Algebraic dot product formula.** a·b = Σ aᵢbᵢ, the sum of products of corresponding components. In R³, a·b = a₁b₁ + a₂b₂ + a₃b₃. In Einstein notation this is aᵢbᵢ. The two definitions agree because |a||b|cos θ equals the sum of component products when the vectors are written in an orthonormal basis.

**Properties.** The dot product is commutative, distributive, and bilinear: a·b = b·a, a·(b + c) = a·b + a·c, and (αa)·b = α(a·b). It is positive definite, a·a = |a|², and zero exactly when a = 0 or b = 0 or a ⊥ b.

**Orthogonal vector identification.** Two nonzero vectors are orthogonal (perpendicular) when a·b = 0. To test whether vectors are orthogonal, compute the dot product and check whether it vanishes. In R³ the unit vectors i, j, k are mutually orthogonal, i·j = i·k = j·k = 0.

**Vector projection calculation.** The scalar projection of a onto b is a·b / |b|, and the vector projection is

proj_b a = (a·b / |b|²) b.

It is the component of a lying along b, the foot of the perpendicular from a to the line through b. The vector rejection of a from b, a − proj_b a, is the component of a perpendicular to b, so a decomposes uniquely into the sum of its projection onto b and its rejection.

**Cauchy–Schwarz inequality.** |a·b| ≤ |a||b|, with equality if and only if a and b are linearly dependent (one is a scalar multiple of the other). Proof sketch: the expression a·b − t(a·a) is a nonnegative quadratic in t whose discriminant is nonpositive, which yields (a·b)² ≤ (a·a)(b·b). Taking square roots gives the result.

**Triangle inequality proof.** |a + b| ≤ |a| + |b|, with equality exactly when a and b point in the same direction. Proof: |a + b|² = (a + b)·(a + b) = |a|² + 2a·b + |b|² ≤ |a|² + 2|a||b| + |b|² = (|a| + |b|)², where the middle step uses Cauchy–Schwarz, a·b ≤ |a||b|.

**Direction cosines applications.** If a makes angles α, β, γ with the coordinate axes, its direction cosines are cos α = a₁/|a|, cos β = a₂/|a|, cos γ = a₃/|a|, and cos²α + cos²β + cos²γ = 1. The direction-cosine matrix of a rotation carries one orthonormal basis to another.

**Worked example.** Let a = (1, 2, 3) and b = (4, −1, 2). Then a·b = 4 − 2 + 6 = 8, |a| = √14, |b| = √21, so cos θ = 8/√294. The projection of a onto b is (8/21) b = (32/21, −8/21, 16/21). Cauchy–Schwarz gives |8| ≤ √14·√21 = √294, true since 64 < 294.

**Exercises.**
1. Find the angle between (1, 1, 0) and (1, 0, 1).
2. Find an orthogonal pair of vectors with components from {−3,−1,1,2,3}.
3. Compute the projection of (1, 2) onto (3, 1).
4. Verify the triangle inequality for a = (1, 0), b = (0, 1).

---

## 3. Vector Cross Product

The cross product of two vectors in R³ returns a vector perpendicular to both. It measures oriented area and encodes rotation, distinguishing it from the dot product, which measures alignment.

**Cross product geometric definition.** a×b = |a||b| sin θ n, where θ is the angle between a and b and n is the unit vector perpendicular to the plane containing them, determined by the right-hand rule. The magnitude equals the area of the parallelogram the two vectors span.

**Determinant formula calculation.** The components of a×b are

a×b = (a₂b₃ − a₃b₂, a₃b₁ − a₁b₃, a₁b₂ − a₂b₁).

This is the expansion of the 3×3 determinant with i, j, k in the top row and a, b as the other two rows:

a×b = |i  j  k; a₁ a₂ a₃; b₁ b₂ b₃|.

**Area of parallelogram calculation.** |a×b| = |a||b| sin θ is the area of the parallelogram spanned by a and b. The area of the triangle they span is half that, |a×b|/2.

**Torque physics applications.** Torque τ = r×F, where r is the position vector from the pivot and F the applied force. Angular momentum L = r×p, and torque is its time derivative, τ = dL/dt. The magnetic force on a moving charge is F = qv×B. In each case the result is perpendicular to the input vectors and its magnitude scales with sin θ.

**Triple scalar product.** The scalar triple product (a×b)·c is the signed volume of the parallelepiped spanned by a, b, c. It equals the determinant |a b c| of the matrix with rows a, b, c, and it is zero exactly when the three vectors are coplanar. It is also cyclic: (a×b)·c = (b×c)·a = (c×a)·b. The related vector triple product a×(b×c) is not associative and obeys the bac-cab rule: a×(b×c) = b(a·c) − c(a·b). This identity is the standard tool for expanding nested cross products.

**Right hand rule convention.** Point the fingers of the right hand along a, curl them toward b; the thumb points along a×b. This fixes the orientation. Reversing the order reverses the result: a×b = −(b×a).

**Orthogonal vector generation.** Given two non-parallel vectors a and b, a×b is orthogonal to both. This gives a quick way to build a normal vector to a plane: take two direction vectors in the plane and cross them.

**Properties.** The cross product is anticommutative, distributive, and obeys (αa)×b = α(a×b). It is zero when a and b are parallel, and a×a = 0. The result is a pseudovector, which does not change sign under reflection of the coordinate system.

**Worked example.** Let u = (1, 2, 3) and v = (4, 5, 6). Then u×v = (2·6 − 3·5, 3·4 − 1·6, 1·5 − 2·4) = (−3, 6, −3). Its magnitude is √(9+36+9) = √54 = 3√6, the parallelogram area. With w = (1, 0, 0), the scalar triple product (u×v)·w = −3, the signed volume.

**Exercises.**
1. Compute (2, 1, −1) × (1, 3, 2) and its magnitude.
2. Find the area of the triangle with vertices (0,0,0), (1,2,0), (0,1,3).
3. Use the right-hand rule to give the direction of i×j and j×i.
4. Compute the scalar triple product of (1,0,0), (0,1,0), (0,0,1).

---

## 4. Vector Spaces

A vector space abstracts the operations of Rⁿ into a structure closed under addition and scalar multiplication. The axioms, subspaces, span, independence, basis, and dimension organize every later argument in the course.

**Vector space axioms.** A vector space is a set V with an addition and a scalar multiplication over a field F, satisfying ten axioms for u, v, w in V and scalars a, b:
1. Closure: u + v ∈ V.
2. Commutativity: u + v = v + u.
3. Associativity: (u + v) + w = u + (v + w).
4. Additive identity: there is 0 with u + 0 = u.
5. Additive inverse: for each u there is −u with u + (−u) = 0.
6. Scalar closure: au ∈ V.
7. Distributivity: a(u + v) = au + av.
8. Scalar associativity: a(bu) = (ab)u.
9. Identity scalar: 1·u = u.
10. Zero scalar: 0·u = 0.

Rⁿ, the space of polynomials of degree at most n, the m×n matrices, and function spaces are the standard examples.

**Subspace testing criteria.** A subset W of a vector space V is a subspace when three conditions hold: W contains the zero vector, W is closed under addition, and W is closed under scalar multiplication. These are necessary and sufficient, because they ensure W inherits the eight axioms from V.

**Linear combination concepts.** A linear combination of v₁, …, vₖ is a sum c₁v₁ + … + cₖvₖ with scalars cᵢ. Linear combinations are the only operations vector spaces provide, and every statement in the subject reduces to them.

**Span of vectors.** The span of a set S is the set of all finite linear combinations of its vectors, the smallest subspace containing S. It is written span(S). If S = {v₁, …, vₖ}, then span(S) = {c₁v₁ + … + cₖvₖ}.

**Linear independence definition.** A set {v₁, …, vₖ} is linearly independent when the only combination c₁v₁ + … + cₖvₖ = 0 is the trivial one, cᵢ = 0 for all i. Equivalently, the matrix with the vectors as columns has full column rank k. If some nontrivial combination gives 0, the set is dependent.

**Basis vector sets.** A basis of V is a set that is linearly independent and spans V. Every basis of a given space has the same size. The standard basis of Rⁿ is {e₁, …, eₙ} with eᵢ having a 1 in the i-th slot and 0 elsewhere. Any set of n independent vectors in Rⁿ is a basis, as is any spanning set of n vectors.

**Dimension of spaces.** The dimension of V is the number of vectors in any basis of V. Rⁿ has dimension n. The space of m×n matrices has dimension mn, and the space of polynomials of degree at most n has dimension n + 1. In Rⁿ, any set of more than n vectors is dependent, and any set of fewer than n vectors cannot span Rⁿ.

**Worked example.** Test {(1,0), (0,1), (1,1)} for independence. Solve c₁(1,0) + c₂(0,1) + c₃(1,1) = 0. The first component gives c₁ + c₃ = 0, the second c₂ + c₃ = 0. There are nonzero solutions, for example c₃ = −1, c₁ = 1, c₂ = 1, so the set is dependent; indeed (1,1) = (1,0) + (0,1). The span of any two of them is all of R², so a basis has two vectors and dim R² = 2.

**Exercises.**
1. Test whether {(1,2,3), (4,5,6), (7,8,9)} is linearly independent.
2. Find the dimension of the space of 2×2 symmetric matrices.
3. Show that {(1,0), (0,1)} is a basis of R².

---

## 5. Fundamental Subspaces

For an m×n matrix A, four subspaces carry the structure of the linear map x ↦ Ax. They are the column space, the row space, the null space, and the left null space. Their dimensions satisfy the rank-nullity theorem.

**Column space definition.** The column space, or image or range, of A is the set of all linear combinations of the columns, a subspace of Rᵐ. It is the set {Ax : x ∈ Rⁿ}, all outputs of the map.

**Row space properties.** The row space is the set of all linear combinations of the rows, a subspace of Rⁿ. It equals the column space of Aᵀ, and it is unchanged by row operations, so the row space of A equals that of any row echelon form of A.

**Null space calculation.** The null space, or kernel, of A is {x : Ax = 0}. To compute it, row-reduce A to echelon form, identify the free variables, and parameterize the solution. Each free variable contributes one dimension to the null space, and each nonzero null-space vector is an eigenvector with eigenvalue 0.

**Left null space properties.** The left null space of A is {y : Aᵀy = 0}, a subspace of Rᵐ. It is the orthogonal complement of the column space: every y in the left null space is orthogonal to every column of A, so Aᵀy = 0 means y·aᵢ = 0 for each column aᵢ.

**Rank of matrix.** The rank of A is the dimension of the column space, equal to the number of pivots in row echelon form, equal to the dimension of the row space. Rank counts the number of independent columns (and rows).

**Nullity of matrix.** The nullity of A is the dimension of the null space, equal to the number of free variables in Ax = 0.

**Rank nullity theorem.** For an m×n matrix A,

rank(A) + nullity(A) = n.

Proof: row-reduce A to echelon form with k pivots. The k pivots give a k-dimensional column and row space, so rank(A) = k. The n − k non-pivot columns are free, so the null space has dimension n − k and nullity(A) = n − k. The two sum to n. Consequences: an n×n matrix is invertible exactly when rank(A) = n and nullity(A) = 0; an m×n matrix whose rank is m has columns that span Rᵐ; and the solution space of a consistent system Ax = b has dimension n − rank(A).

**Worked example.** For A = [[1, 2], [2, 4]], row-reduction gives [[1, 2], [0, 0]], so rank(A) = 1. The null space solves x + 2y = 0, giving x = −2y, so the null space is span{(−2, 1)} and nullity(A) = 1. Rank plus nullity is 1 + 1 = 2, the number of columns. The column space is span{(1, 2)}, a line in R², and the left null space is span{(2, −1)}, the line orthogonal to it.

**Exercises.**
1. For A = [[1, 1, 1], [2, 3, 4]], find rank, nullity, and a null-space basis.
2. Show the left null space of A is the orthogonal complement of its column space.

**Dimensional census.** For an m × n matrix A of rank r, the four fundamental subspaces decompose the domain and codomain into pairs of orthogonal complements:

| Subspace | Definition | Ambient space | Dimension |
|---|---|---|---|
| Column space C(A) | All combinations of the columns, the range of Ax. | Rᵐ | r |
| Row space C(Aᵀ) | All combinations of the rows, the column space of Aᵀ. | Rⁿ | r |
| Null space N(A) | Solutions of Ax = 0, the kernel. | Rⁿ | n − r |
| Left null space N(Aᵀ) | Solutions of Aᵀy = 0, orthogonal to the column space. | Rᵐ | m − r |

The row space and null space are orthogonal complements in Rⁿ; the column space and left null space are orthogonal complements in Rᵐ. These direct sums, Rⁿ = C(Aᵀ) ⊕ N(A) and Rᵐ = C(A) ⊕ N(Aᵀ), together with the rank-nullity identity r + (n − r) = n, give a complete picture of how a matrix acts.

---

## 6. Inner Product Spaces

An inner product generalizes the dot product to arbitrary vector spaces, giving length, angle, and orthogonality. The Cauchy–Schwarz and triangle inequalities follow, and orthonormal bases are built by Gram–Schmidt.

**Inner product axioms.** An inner product on a vector space V is a function ⟨·,·⟩ assigning to each pair u, v a scalar, satisfying:
1. Symmetry: ⟨u, v⟩ = ⟨v, u⟩ (conjugate symmetry for complex spaces).
2. Linearity: ⟨au + bv, w⟩ = a⟨u, w⟩ + b⟨v, w⟩.
3. Positive-definiteness: ⟨u, u⟩ ≥ 0, with equality only for u = 0.

The standard examples are Rⁿ with the dot product, Cⁿ with ⟨u, v⟩ = Σ uᵢv̄ᵢ, and L² spaces with ⟨f, g⟩ = ∫ fḡ. On Rⁿ an inner product can also be written as xᵀAx for a symmetric positive-definite matrix A, with the ordinary dot product recovered when A is the identity. This matrix-weighted form underlies the Mahalanobis distance and the study of non-Euclidean metrics on Euclidean space.

**Cauchy–Schwarz in inner products.** |⟨u, v⟩| ≤ ‖u‖‖v‖, with equality exactly when u and v are linearly dependent. Proof: the quantity ⟨u, v⟩ − t⟨u, u⟩ is a nonnegative function of t, so its discriminant is nonpositive, which gives (⟨u, v⟩)² ≤ ⟨u, u⟩⟨v, v⟩.

**Norm induced by inner product.** ‖u‖ = √⟨u, u⟩. This is the length of u, and it satisfies the triangle inequality ‖u + v‖ ≤ ‖u‖ + ‖v‖ as a consequence of Cauchy–Schwarz. When the induced metric is complete, the space is a Hilbert space; otherwise it is a pre-Hilbert space.

**Orthogonal sets of vectors.** A set {u₁, …, uₖ} is orthogonal when ⟨uᵢ, uⱼ⟩ = 0 for all i ≠ j. Two subspaces U and W of V are orthogonal when every element of U is orthogonal to every element of W. Orthogonal vectors are automatically linearly independent: if Σ cᵢuᵢ = 0, then taking the inner product with uⱼ gives cⱼ⟨uⱼ, uⱼ⟩ = 0, hence cⱼ = 0.

**Orthonormal basis construction.** An orthonormal set satisfies ⟨eᵢ, eⱼ⟩ = δᵢⱼ, so the vectors are mutually perpendicular and each has length 1. It is a basis for the subspace it spans, and it is convenient because the projection of v onto that subspace is Σ⟨v, eⱼ⟩eⱼ. Orthonormal bases also appear as the eigenvector set of a symmetric matrix, where eigenvectors of distinct eigenvalues are already orthogonal.

**Gram Schmidt orthogonalization.** Given a linearly independent set {v₁, …, vₙ}, the Gram-Schmidt process builds an orthonormal set {e₁, …, eₙ} spanning the same subspace:

u₁ = v₁, e₁ = u₁/‖u₁‖
u₂ = v₂ − ⟨v₂, e₁⟩e₁, e₂ = u₂/‖u₂‖
u₃ = v₃ − ⟨v₃, e₁⟩e₁ − ⟨v₃, e₂⟩e₂, e₃ = u₃/‖u₃‖, and so on.

Each uₖ removes from vₖ its components along all previous eⱼ, leaving the new orthogonal direction. The process always succeeds as long as the input set is independent, since no uₖ is zero.

**Orthogonal complement spaces.** For a subspace W of V, the orthogonal complement W⊥ = {v ∈ V : v·w = 0 for all w ∈ W}. Then W and W⊥ are subspaces, W ∩ W⊥ = {0}, and when V is finite-dimensional, V = W ⊕ W⊥ with dim W + dim W⊥ = dim V.

**Worked example.** Orthonormalize {(1, 1, 0), (1, −1, 0)}. First e₁ = (1, 1, 0)/√2. Then u₂ = (1, −1, 0) − ⟨(1,−1,0), (1/√2, 1/√2, 0)⟩e₁ = (1, −1, 0) − 0 = (1, −1, 0), and e₂ = (1, −1, 0)/√2. The set {(1/√2, 1/√2, 0), (1/√2, −1/√2, 0)} is orthonormal. The orthogonal complement of the xy-plane in R³ is the z-axis, span{(0,0,1)}.

**Exercises.**
1. Orthonormalize {(1, 1), (1, 0)} by Gram–Schmidt.
2. Find the orthogonal complement of span{(1, 1, 1)} in R³.
3. Show that the eigenvectors of a symmetric matrix with distinct eigenvalues are orthogonal.

---

## 7. Coordinate Systems

This section moves from a fixed coordinate frame to a changed one, and then to the dual viewpoint, where vectors and linear functionals are the central objects.

**Standard coordinate systems.** A Cartesian system locates a point by real coordinates, (x, y) in two dimensions and (x, y, z) in three. The axes divide the space into quadrants (or octants in R³). The position vector of a point is the vector from the origin to that point, and a vector is given by its components in the standard basis. Distances follow from the Pythagorean formula, d = √(Σ (xᵢ − yᵢ)²).

**Change of basis matrix.** For two bases B and B′ of the same space, the change-of-basis matrix P from B′ to B has, as its columns, the B-coordinates of the B′ basis vectors. Coordinates transform by [v]_B = P [v]_B′. The matrix P is always invertible, since a basis change is a bijection on coordinates.

**Coordinate transformation formulas.** If A represents a linear map in the basis B, then in the basis B′ the same map is represented by A′ = P⁻¹AP. These matrices are similar and share their invariants: trace, determinant, and eigenvalues. In two and three dimensions a change of basis corresponds to a rotation or reflection of the coordinate frame, and a rotation by θ sends coordinates as x′ = x cos θ − y sin θ, y′ = x sin θ + y cos θ.

**Isomorphism of vector spaces.** An isomorphism is a bijective linear map between two vector spaces. Two finite-dimensional spaces are isomorphic if and only if they have the same dimension. Any choice of bases gives an isomorphism: map the i-th basis vector of one space to the i-th basis vector of the other. All n-dimensional spaces over the same field are therefore structurally the same, and Rⁿ is the universal model of an n-dimensional space.

**Dual space concepts.** The dual space V* of V is the set of all linear functionals on V, maps f: V → F that preserve addition and scalar multiplication. If V is n-dimensional with basis {e₁, …, eₙ}, then V* is also n-dimensional. The dual basis {e₁*, …, eₙ*} is defined by eᵢ*(eⱼ) = δᵢⱼ, and every functional f writes as f(v) = Σ f(eᵢ)eᵢ*(v). The bidual V** is naturally isomorphic to V: the map that sends each vector v to the functional on V* defined by f ↦ f(v) is an isomorphism that does not depend on any choice of basis, whereas identifying V with its single dual V* does require choosing a basis. This distinction between a natural isomorphism and a basis-dependent one is a recurring theme in the subject.

**Linear functionals.** A linear functional is a map f: V → F that is linear. The space of all of them is V*, and its dimension equals dim V. If T: V → W is a linear map with matrix A, then its dual T*: W* → V* is given by (T*f)(v) = f(Tv) and is represented by Aᵀ. The gradient of a smooth function on V is an element of V*: it is the functional that maps a direction to the directional derivative.

**Annihilator subspaces.** For a subspace W of V, the annihilator W⁰ = {f ∈ V* : f(w) = 0 for all w ∈ W} is a subspace of V*. It consists of all linear functionals that vanish on W. In finite dimensions, dim W + dim W⁰ = dim V, so the annihilator plays the dual role of the orthogonal complement: just as W⊥ is the set of vectors orthogonal to W, W⁰ is the set of functionals zero on W. For a subspace of Rⁿ given by linear equations, its annihilator is exactly the solution space of those equations.

**Worked example.** Let V = R² and B = {(1, 0), (0, 1)}. A second basis B′ = {(1, 1), (1, −1)} gives P from B′ to B as [[1, 1], [1, −1]]. A vector v with B′-coordinates (a, b) has B-coordinates (a + b, a − b). The dual basis of B′ is {e₁*, e₂*} with e₁* = (1/2, 1/2) and e₂* = (1/2, −1/2), so e₁*(1,0) = e₁*(0,1) = 1/2 and e₂*(1,0) = 1/2, e₂*(0,1) = −1/2. The annihilator of the line span{(1, 1)} is the set of functionals (p, q) with p + q = 0, i.e. the line span{(1, −1)} in V*.

**Exercises.**
1. Given P = [[1, 1], [0, 1]], find [v]_B′ if [v]_B = (1, 0).
2. Write the dual functional that sends (x, y) to x + 2y and give its matrix.
3. Find the annihilator of the plane x + y + z = 0 in R³.

---

## 8. Summary

The article moves from concrete to abstract in the order a short course takes. Section 1 fixes the seven elementary operations that make Rⁿ a vector space. Sections 2 and 3 add the dot and cross products, which measure alignment and oriented area respectively. Section 4 abstracts to the axioms and to subspaces, span, independence, basis, and dimension. Section 5 reads a matrix through its four fundamental subspaces and the rank-nullity theorem. Section 6 adds length and angle, with orthonormal bases and Gram–Schmidt. Section 7 changes the coordinate frame, moves to the dual viewpoint, and closes with annihilators.

The recommended study order for the S01 module is the section order above, one subtopic at a time, with the exercises at the end of each section as the practice component of the two-hour daily template. The full 49-concept checklist of the module maps to the subsections in the order presented.

---

## References

The sources are listed in full in `s01-reference.md`, organized under the eight subtopic headings. The primary entries are Euclidean vector, dot product, and cross product on Wikipedia; Vector, Dot Product, Cross Product, Vector Space, Span, Null Space, Rank-Nullity Theorem, Inner Product Space, Orthogonal, Orthonormal Basis, Basis, and Dual Space on MathWorld; the Khan Academy Linear Algebra course; intmath vector introductions; the MIT OpenCourseWare 18.06 lectures by Gilbert Strang; the 3Blue1Brown linear algebra series; the Physics Forums vectors guide; Cuemath vector forms; the linearalgebra.org vectors-and-spaces guide; the Math Is Fun matrix introduction; and the Math Warehouse vector tools. Unreachable URLs in that list are replaced by the summaries written here.
