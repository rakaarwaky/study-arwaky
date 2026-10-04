# Linear Algebra — roadmap.sh FULL reference

> Source: https://roadmap.sh/ai/roadmap/linear-algebra-h4gkg
> Title: Linear Algebra — Step by step guide to mastering linear algebra foundations

This is the complete tree. Each `##` section is also a folder here: S01 … S12, each with a plan.md + topics.

---

# Linear Algebra
## Vectors and Spaces
### Vector Fundamentals
- Geometric vector representation
- Algebraic vector representation
- Vector addition operations
- Scalar multiplication rules
- Vector magnitude calculation
- Unit vector normalization
- Position vectors in space
### Vector Dot Product
- Geometric dot product definition
- Algebraic dot product formula
- Orthogonal vector identification
- Vector projection calculation
- Cauchy Schwarz inequality
- Triangle inequality proof
- Direction cosines applications
### Vector Cross Product
- Cross product geometric definition
- Determinant formula calculation
- Area of parallelogram calculation
- Torque physics applications
- Triple scalar product
- Right hand rule convention
- Orthogonal vector generation
### Vector Spaces
- Vector space axioms
- Subspace testing criteria
- Linear combination concepts
- Span of vectors
- Linear independence definition
- Basis vector sets
- Dimension of spaces
### Fundamental Subspaces
- Column space definition
- Row space properties
- Null space calculation
- Left null space properties
- Rank of matrix
- Nullity of matrix
- Rank nullity theorem
### Inner Product Spaces
- Inner product axioms
- Cauchy Schwarz in inner products
- Norm induced by inner product
- Orthogonal sets of vectors
- Orthonormal basis construction
- Gram Schmidt orthogonalization
- Orthogonal complement spaces
### Coordinate Systems
- Standard coordinate systems
- Change of basis matrix
- Coordinate transformation formulas
- Isomorphism of vector spaces
- Dual space concepts
- Linear functionals
- Annihilator subspaces

## Matrices and Operations
### Matrix Fundamentals
- Matrix dimension definition
- Special matrix types
- Zero matrix properties
- Identity matrix properties
- Scalar matrix operations
- Matrix equality criteria
- Partitioned matrices
### Matrix Addition
- Matrix addition rules
- Matrix subtraction rules
- Commutative property of addition
- Associative property of addition
- Zero matrix as identity
- Additive inverse matrices
- Dimensions compatibility check
### Matrix Multiplication
- Multiplication compatibility rules
- Row column product method
- Non commutative property
- Associative property of multiplication
- Distributive property over addition
- Identity matrix multiplication
- Powers of square matrices
### Matrix Transpose
- Transpose operation definition
- Transpose of sum property
- Transpose of product property
- Symmetric matrix identification
- Skew symmetric matrices
- Orthogonal matrix properties
- Trace of matrix
### Block Matrices
- Block matrix multiplication
- Block diagonal matrices
- Block triangular matrices
- Inversion of block matrices
- Determinant of partitioned matrices
- Kronecker product definition
- Hadamard product definition
### Matrix Types
- Diagonal matrices
- Triangular matrices
- Symmetric matrices
- Skew symmetric matrices
- Idempotent matrices
- Nilpotent matrices
- Orthogonal matrices

## Systems of Equations
### Linear Equations
- Linear equation definition
- Solutions of linear equations
- Geometric interpretation of lines
- Inconsistent system identification
- Dependent system identification
- Independent system identification
- Parameterized solution sets
### Augmented Matrices
- System to matrix conversion
- Elementary row operations
- Row equivalence concept
- Matrix representation of systems
- Variable elimination method
- Backward substitution process
- Consistency criteria
### Gaussian Elimination
- Forward elimination steps
- Row echelon form definition
- Pivot position identification
- Free variable identification
- General solution writing
- Particular solution finding
- Homogeneous system solutions
### Gauss Jordan Elimination
- Reduced row echelon form
- Leading ones creation
- Zeroing above and below pivots
- Matrix inversion via elimination
- Rank determination via pivots
- Uniqueness of reduced form
- Computational complexity analysis
### Homogeneous Systems
- Homogeneous system definition
- Trivial solution concept
- Non trivial solution existence
- Null space connection
- Dimension of solution space
- Superposition principle
- Basis for solution space
### Matrix Equations
- Matrix vector product equations
- Linear system as matrix equation
- Inverse matrix solution method
- Cramer rule application
- Conditioning of linear systems
- Sensitivity analysis
- Residual vector calculation
### Applications of Systems
- Network flow problems
- Electrical circuit analysis
- Chemical equation balancing
- Economic input output models
- Polynomial curve fitting
- Finite difference methods
- Traffic flow modeling

## Determinants
### Determinant Fundamentals
- Determinant geometric meaning
- Determinant of scalar
- Two by two determinant
- Three by three determinant
- Expansion by minors
- Cofactor expansion method
- Sign pattern chessboard
### Properties of Determinants
- Determinant of transpose
- Determinant of product
- Effect of row swapping
- Effect of scaling a row
- Effect of adding row multiples
- Determinant of inverse matrix
- Determinant of triangular matrix
### Cofactor Expansion
- Minor matrix definition
- Cofactor definition and signs
- Expansion along any row
- Expansion along any column
- Adjoint matrix definition
- Inverse via adjoint matrix
- Cramer rule derivation
### Geometric Applications
- Area of parallelogram in plane
- Volume of parallelepiped in space
- Orientation of coordinate systems
- Linear transformation scaling factor
- Jacobian determinant introduction
- Determinant zero meaning
- Cross product via determinant

## Eigenvalues and Eigenvectors
### Eigenvalue Fundamentals
- Eigenvalue eigenvector equation
- Characteristic polynomial derivation
- Trace and determinant connection
- Spectrum of a matrix
- Eigenspace definition
- Geometric multiplicity
- Algebraic multiplicity
### Characteristic Equation
- Setting up characteristic equation
- Finding roots of polynomial
- Cayley Hamilton theorem
- Invariant subspaces
- Spectral radius definition
- Gershgorin circle theorem
- Schur triangulation theorem
### Diagonalization
- Diagonalizable matrix definition
- Condition for diagonalizability
- Diagonalization formula
- Similarity transformation
- Computing matrix powers
- Matrix exponential calculation
- Simultaneous diagonalization
### Complex Eigenvalues
- Complex number review
- Complex eigenvalues occurrence
- Complex eigenvectors calculation
- Rotation scaling representation
- Real canonical forms
- Jordan canonical form introduction
- Spectral theorem for real matrices
### Quadratic Forms
- Quadratic form definition
- Symmetric matrix association
- Positive definite matrices
- Negative definite matrices
- Indefinite matrices
- Principal axis theorem
- Sylvester criterion

## Linear Transformations
### Transformation Fundamentals
- Function mapping definition
- Linear transformation axioms
- Kernel of transformation
- Range of transformation
- Rank nullity theorem proof
- One to one transformations
- Onto transformations
### Matrix Representation
- Standard matrix of transformation
- Transformation of basis
- Composition of transformations
- Inverse transformations
- Change of basis for operators
- Similarity of matrices
- Coordinate isomorphism
### Geometric Transformations
- Scaling transformations in plane
- Rotation transformations in plane
- Reflection transformations in plane
- Shear transformations in plane
- Translation affine extension
- Projection transformations
- Composition of geometric operations
### Orthogonal Transformations
- Orthogonal operator definition
- Preservation of inner product
- Length preservation property
- Orthogonal matrix representation
- Reflection across subspace
- Rotation in higher dimensions
- Rigid body motions

## Orthogonality
### Orthogonal Sets
- Orthogonal vector sets
- Orthonormal vector sets
- Linear independence of orthogonal sets
- Coordinate extraction formula
- Parseval identity
- Bessel inequality
- Orthogonal projection formula
### Gram Schmidt Process
- Orthogonalization algorithm steps
- Normalization step
- QR decomposition introduction
- Modified Gram Schmidt method
- Numerical stability issues
- Householder reflections method
- Givens rotations method
### Orthogonal Projections
- Projection onto subspace
- Projection matrix construction
- Orthogonal decomposition theorem
- Distance from point to subspace
- Least squares approximation
- Normal equations derivation
- Pseudoinverse calculation
### QR Decomposition
- QR factorization definition
- Gram Schmidt based QR
- Householder triangularization
- Solving systems using QR
- Least squares via QR
- Eigenvalue computation via QR
- Uniqueness of QR decomposition

## Matrix Factorizations
### LU Decomposition
- LU factorization definition
- Doolittle algorithm method
- Crout algorithm method
- Lower triangular matrix L
- Upper triangular matrix U
- Permutation matrix P
- Solving systems using LU
### Cholesky Decomposition
- Cholesky factorization definition
- Positive definiteness requirement
- Lower triangular factor L
- Algorithm for Cholesky factors
- Computational efficiency benefits
- Applications in statistics
- Solving normal equations
### Spectral Decomposition
- Spectral theorem statement
- Orthogonal diagonalizability
- Eigendecomposition of symmetric matrices
- Spectral projection operators
- Principal component analysis foundation
- Matrix norm via eigenvalues
- Rayleigh quotient properties
### Singular Value Decomposition
- SVD definition and existence
- Singular values calculation
- Left singular vectors
- Right singular vectors
- SVD matrix representation
- Relation to eigendecomposition
- Low rank matrix approximation
### Principal Component Analysis
- PCA conceptual overview
- Covariance matrix calculation
- Variance maximization view
- Dimensionality reduction steps
- Data projection via SVD
- Principal components interpretation
- Noise filtering applications

## Advanced Topics
### Jordan Canonical Form
- Generalized eigenvectors
- Jordan chains construction
- Nilpotent operators structure
- Jordan block definition
- Transformation to Jordan form
- Minimal polynomial concept
- Applications of Jordan form
### Matrix Calculus
- Derivative of scalar with vector
- Derivative of vector with vector
- Derivative of scalar with matrix
- Gradient vector calculation
- Hessian matrix calculation
- Matrix differentiation rules
- Optimization applications
### Tensor Algebra
- Tensor definition and rank
- Contraction operations
- Tensor product definition
- Change of basis for tensors
- Symmetric and antisymmetric tensors
- Outer product of tensors
- Applications in physics
### Positive Definite Matrices
- Characterizations of positive definiteness
- Principal minors test
- Cholesky connection
- Min max theorem
- Courant Fischer minimax theorem
- Simultaneous diagonalization of pairs
- Ellipsoid geometry applications
### Norms and Condition Numbers
- Vector norms vector spaces
- Matrix norms induced norms
- Frobenius norm definition
- Operator norm properties
- Condition number of matrix
- Ill conditioned systems
- Error bounds estimation

## Numerical Methods
### Floating Point Arithmetic
- Floating point representation
- Roundoff error introduction
- Machine epsilon concept
- Numerical stability definition
- Forward error analysis
- Backward error analysis
- Overflow and underflow
### Iterative Methods
- Stationary iterative methods
- Jacobi method algorithm
- Gauss Seidel method algorithm
- Successive overrelaxation method
- Convergence criteria for iterations
- Spectral radius condition
- Preconditioning techniques
### Krylov Subspace Methods
- Krylov subspace definition
- Arnoldi iteration method
- Lanczos iteration method
- Conjugate gradient method
- GMRES algorithm
- BiCGSTAB method
- Convergence analysis
### Eigenvalue Algorithms
- Power iteration method
- Inverse iteration method
- Rayleigh quotient iteration
- QR algorithm for eigenvalues
- Shift strategies in QR
- Lanczos algorithm for symmetric
- Divide and conquer methods

## Applications
### Computer Graphics
- Homogeneous coordinates in graphics
- 2D transformation matrices
- 3D transformation matrices
- Perspective projection matrices
- Orthographic projection matrices
- Viewport transformation
- Camera matrix calculation
### Machine Learning Foundations
- Feature matrix representation
- Linear regression via matrices
- Logistic regression setup
- Support vector machines basis
- Neural network layer operations
- Word embeddings spatial models
- Collaborative filtering matrices
### Graph Theory Connections
- Adjacency matrix of graph
- Incidence matrix of graph
- Laplacian matrix definition
- Degree matrix calculation
- Spectral graph theory basics
- Random walks on graphs
- PageRank algorithm derivation
### Control Theory
- State space representation
- Controllability matrix rank
- Observability matrix rank
- Lyapunov stability analysis
- Pole placement technique
- Linear quadratic regulator
- Transfer function connection

## Computational Linear Algebra
### Software Libraries
- BLAS library standards
- LAPACK library routines
- Eigen C++ library usage
- NumPy array operations
- SciPy linalg module
- MATLAB matrix syntax
- Julia linear algebra ecosystem
### Performance Optimization
- Memory hierarchy considerations
- Cache locality in loops
- Loop unrolling techniques
- Parallel matrix multiplication
- GPU acceleration basics
- Sparse matrix storage formats
- Banded matrix optimization

= Related Roadmaps
- Calculus Basics
- Multivariable Calculus
- Probability and Statistics
- Optimization Methods

= Backlink