# Systems of Linear Equations

## Abstract

This article develops systems of linear equations and their matrix
representation. It proceeds from single linear equations and geometric
interpretation, through augmented matrices, Gaussian and Gauss-Jordan
elimination, homogeneous systems, matrix equations, to applications in
networks, circuits, chemistry, economics, and interpolation. Every section
states the definition, the principal identities, a worked example, and an
exercise. The article covers the full S03 module checklist of 49 concepts
across 7 subtopics.

**Keywords:** linear equation, system of equations, augmented matrix,
elementary row operations, row echelon form, reduced row echelon form,
Gaussian elimination, Gauss-Jordan elimination, homogeneous system, matrix
equation, Cramer's rule, network flow, circuit analysis, curve fitting.

---

## 1. Linear Equations

A linear equation in variables x₁, …, xₙ has the form a₁x₁ + … + aₙxₙ = b
with constant coefficients aᵢ and constant b. A system is a collection of
such equations sharing the same variables.

**Linear equation definition.** an equation a₁x₁ + … + aₙxₙ = b where the
variables appear only to the first power and are not multiplied together.

**Solutions of linear equations.** A solution is an n-tuple (x₁, …, xₙ)
that satisfies the equation. A system's solution is an n-tuple satisfying
every equation simultaneously.

**Geometric interpretation of lines.** In two variables, each linear
equation is a line in the plane; a solution is an intersection point of all
lines. In three variables, each equation is a plane in 3D space.

**Inconsistent system identification.** A system is inconsistent when it
has no solution — geometrically, parallel lines/planes with no common
intersection.

**Dependent system identification.** A system is dependent when at least
one equation is a linear combination of the others, giving infinitely many
solutions.

**Independent system identification.** A system is independent when no
equation is a combination of the others; with n equations in n variables it
typically has a unique solution.

**Parameterized solution sets.** When a system has infinitely many
solutions, the free variables serve as parameters and the solution set is
written parametrically.

**Worked example.** x + y = 3 and x − y = 1 give x = 2, y = 1 — a unique
solution (the lines intersect at (2, 1)). x + y = 3 and 2x + 2y = 6 are
dependent (the same line). x + y = 3 and x + y = 4 are inconsistent
(parallel lines).

**Exercises.**
1. Solve x + 2y = 5, 3x − y = 4.
2. Is x + y = 2, 2x + 2y = 5 consistent?
3. Write the solution set of x + y + z = 1 parametrically.

---

## 2. Augmented Matrices

An augmented matrix [A | b] bundles the coefficient matrix A and the
right-hand side vector b into one matrix. Elementary row operations on it
correspond to valid manipulations of the system.

**System to matrix conversion.** Write coefficients of each variable as
columns of A and append b as the last column: [A | b].

**Elementary row operations.** (1) Swap two rows. (2) Multiply a row by a
nonzero scalar. (3) Add a multiple of one row to another. These preserve
the solution set.

**Row equivalence concept.** Two matrices are row equivalent when one can be
obtained from the other by elementary row operations. Row-equivalent
augmented matrices represent systems with the same solutions.

**Matrix representation of systems.** A system Ax = b is represented by the
augmented matrix [A | b]; solving the system means row-reducing [A | b].

**Variable elimination method.** Use row operations to eliminate variables
from equations, reducing to triangular form solvable by back substitution.

**Backward substitution process.** Starting from the last equation of a
triangular system, solve for the last variable and substitute upward.

**Consistency criteria.** A system is consistent exactly when row reduction
does not produce a row [0 … 0 | c] with c ≠ 0 in the augmented matrix.

**Worked example.** x + y = 3, x − y = 1 → [1 1 | 3; 1 −1 | 1] → row2 −
row1 gives [1 1 | 3; 0 −2 | −2] → y = 1, x = 2.

**Exercises.**
1. Write the augmented matrix for 2x + 3y = 5, x − y = 1.
2. Row-reduce [1 2 | 3; 2 4 | 7] and state consistency.
3. Solve via augmented matrix: x + y = 4, 2x − y = 5.

---

## 3. Gaussian Elimination

Gaussian elimination applies elementary row operations to reach row echelon
form, then uses back substitution to find the general solution.

**Forward elimination steps.** Use row operations to create zeros below each
pivot, progressing left to right, producing row echelon form.

**Row echelon form definition.** (1) All zero rows are at the bottom. (2)
Each leading entry (pivot) of a row is to the right of pivots above it.
(3) All entries below a pivot are zero.

**Pivot position identification.** A pivot position is the location of the
leading entry of a row in row echelon form; pivot columns contain pivots.

**Free variable identification.** Variables corresponding to non-pivot
columns are free; they can take any value and parameterize solutions.

**General solution writing.** Express pivot variables in terms of free
variables; write the solution set parametrically.

**Particular solution finding.** Set all free variables to 0 and solve for
pivot variables to obtain one particular solution.

**Homogeneous system solutions.** Ax = 0 always has the trivial solution
x = 0; nontrivial solutions exist exactly when there are free variables.

**Worked example.** [1 2 3 | 6; 2 4 5 | 8] → row2 − 2·row1 = [0 0 −1 |
−4] → z = 4, y free, x = 6 − 2y − 3·4 = −6 − 2y. Solution:
(x, y, z) = (−6, 0, 4) + y(−2, 1, 0).

**Exercises.**
1. Row-reduce [1 2 | 5; 3 4 | 6] to row echelon form.
2. Identify pivot and free columns of [1 0 2 3 | 1; 0 1 −1 2 | 0].
3. Write the general solution of x + 2y + 3z = 6.

---

## 4. Gauss-Jordan Elimination

Gauss-Jordan elimination continues row reduction to reduced row echelon
form (RREF), where each pivot is 1 and is the only nonzero entry in its
column.

**Reduced row echelon form.** Row echelon form plus: each pivot is 1, and
each pivot column contains zeros everywhere else.

**Leading ones creation.** Scale each pivot row so the pivot entry is 1.

**Zeroing above and below pivots.** Use row operations to clear every
non-pivot entry in each pivot column, not only those below.

**Matrix inversion via elimination.** Row-reduce [A | I]; if A is
invertible the result is [I | A⁻¹].

**Rank determination via pivots.** The rank of A equals the number of
pivots (nonzero rows) in its row echelon form.

**Uniqueness of reduced form.** The RREF of a matrix is unique — it does
not depend on the sequence of row operations chosen.

**Computational complexity analysis.** Gaussian/Gauss-Jordan elimination on
an n×n matrix costs O(n³) arithmetic operations.

**Worked example.** [1 2 | 3; 2 4 | 8] → row2 − 2·row1 → [1 2 | 3; 0 0 |
2] → inconsistent (row [0 0 | 2]). For [2 1 | 5; 1 3 | 5] → RREF [1 0 |
2; 0 1 | 1] → x = 2, y = 1.

**Exercises.**
1. Compute the RREF of [[1, 2], [3, 4]].
2. Find the inverse of [[1, 2], [3, 4]] via [A | I] elimination.
3. State the rank of [[1, 2, 3], [2, 4, 6], [1, 1, 1]].

---

## 5. Homogeneous Systems

A homogeneous system has the form Ax = 0 — every right-hand side is zero.
It always has the trivial solution x = 0.

**Homogeneous system definition.** Ax = 0 where 0 is the zero vector.

**Trivial solution concept.** x = 0 is always a solution of Ax = 0.

**Non-trivial solution existence.** Non-trivial solutions exist exactly
when A has fewer pivots than columns (free variables exist), equivalently
when det(A) = 0 for square A.

**Null space connection.** The solution set of Ax = 0 is the null space
(kernel) of A.

**Dimension of solution space.** The dimension of the null space equals
the number of free variables = n − rank(A).

**Superposition principle.** If x and y solve Ax = 0, then so does x + y;
if x solves Ax = 0 then cx solves it for any scalar c.

**Basis for solution space.** A basis of the null space is obtained by
setting each free variable to 1 (others 0) in the parametric solution.

**Worked example.** x + 2y + 3z = 0, 2x + 4y + 6z = 0 → one equation,
two free variables y, z → x = −2y − 3z → solution span{(−2, 1, 0), (−3,
0, 1)}.

**Exercises.**
1. Solve x + y + z = 0 homogeneously.
2. Find a basis for the null space of [[1, 2], [2, 4]].
3. Does [[1, 2, 3], [4, 5, 6]]x = 0 have non-trivial solutions?

---

## 6. Matrix Equations

A system Ax = b is a matrix equation: the unknown vector x is multiplied by
matrix A to produce b. When A is square and invertible, x = A⁻¹b.

**Matrix-vector product equations.** Ax forms a linear combination of the
columns of A with coefficients from x.

**Linear system as matrix equation.** Write coefficients as A, unknowns as
x, right-hand sides as b: Ax = b.

**Inverse matrix solution method.** When A is invertible, x = A⁻¹b is the
unique solution.

**Cramer's rule application.** xᵢ = det(Aᵢ(b)) / det(A), where Aᵢ(b) is A
with column i replaced by b; requires det(A) ≠ 0.

**Conditioning of linear systems.** A well-conditioned system has small
changes in input producing small changes in output; ill-conditioned systems
amplify errors (measured by condition number).

**Sensitivity analysis.** Studies how much the solution x changes when A or
b is perturbed; governed by the condition number of A.

**Residual vector calculation.** For an approximate solution x̃, the
residual is r = b − Ax̃; r = 0 exactly when x̃ is a true solution.

**Worked example.** A = [[2, 1], [1, 2]], b = [3, 3]. det(A) = 3 ≠ 0, so
x = A⁻¹b. A⁻¹ = (1/3)[[2, −1], [−1, 2]] → x = [1, 1]. Check: [2, 1;
1, 2][1, 1] = [3, 3] = b.

**Exercises.**
1. Solve [[2, 1], [1, 2]]x = [3, 3] via inverse.
2. Use Cramer's rule for x + 2y = 3, 3x − y = 4.
3. Compute the residual for x̃ = [1, 1] in the example above.

---

## 7. Applications of Systems

Linear systems model real-world relationships where variables combine
linearly.

**Network flow problems.** Flow conservation at each node gives a linear
system; unknowns are flows on edges.

**Electrical circuit analysis.** Kirchhoff's current and voltage laws give
linear systems for currents and voltages in circuits.

**Chemical equation balancing.** Atom conservation for each element gives a
homogeneous linear system whose solution balances the reaction.

**Economic input-output models.** Leontief models: x = Ax + d, where A is
the input-output matrix and d is final demand.

**Polynomial curve fitting.** Finding coefficients of a polynomial passing
through given points is a linear system (Vandermonde matrix).

**Finite difference methods.** Differential equations discretized on a grid
yield large sparse linear systems.

**Traffic flow modeling.** Conservation of cars at intersections gives
linear systems for traffic flows on streets.

**Worked example.** Circuit: I₁ + I₂ = I₃ (KCL), 2I₁ − 3I₂ = 6 (KVL) →
solve for currents. Chemical: C₃H₈ + O₂ → CO₂ + H₂O balanced via atom
counts gives C₃H₈ + 5O₂ → 3CO₂ + 4H₂O.

**Exercises.**
1. Set up flow conservation equations for a 3-node network.
2. Balance Fe + O₂ → Fe₂O₃ via a linear system.
3. Fit a line y = mx + b through (0,1), (1,3), (2,5) using least squares.

---

## References

Khan Academy Linear Algebra (systems of equations, elimination); MIT
OpenCourseWare 18.06 lectures by Gilbert Strang; 3Blue1Brown linear algebra
series; "Linear Algebra and Its Applications" (Lay); "Introduction to Linear
Algebra" (Strang). Entries: system of linear equations, augmented matrix,
Gaussian elimination, row echelon form, Cramer's rule, homogeneous system,
least squares on Wikipedia and MathWorld.
