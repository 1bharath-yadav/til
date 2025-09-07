## Discourse link
	- https://discourse.onlinedegree.iitm.ac.in/c/courses/9
- ## Notes:
	- https://22f3001517.github.io/mlf-ta-notes/index.html
	- https://www.youtube.com/@visualkernel
	-
- ---
- the null space is called soluton space,in linear regression we said answers by looking at the regrssion line,
	- 1.we project(dot product) the data points onto the null space so that the errors will minimum as we look into dependent variable.
	- $W^TX=b$
	-
	-
- First rule is transformation applied to every point
- Matrix itself is a transformation so ,to manipulate something we change our data into matrix form
- Identity matrix do nothing to the object
- Scalar matrix scales the whole object(all dimensions) K times,
- off-matrix just stretches or squishes the axis where it has k,for diagonal elements equal 1 those axis will remain same,
- Reflection matrix  reflects the axis according to diagonal elements,ex if $X_{11}$ = -2, it reflects the object along x axis and scales 2 times
- Diagonal matrices just combine to produce another matrices
- Multiplication of matrix ❌  ,combined transformation ✔️
- If transformation from $3^d \to \ 2^d$ then lineful of vectors squishes into origin,else $3^d \to \ 1^d$ then whole planeful of vectors squishes into the origin,theese lineful or planeful of vectors spans the null space, where the solutions exist.
- Eigen values trick: $\lambda_1, \lambda_2 = m \pm \sqrt{m^2 - p}$
- $\frac{1}{2} \, \text{tr} \left( \begin{bmatrix} a & b \\ c & d \end{bmatrix} \right) = \frac{a + d}{2} = \frac{\lambda_1 + \lambda_2}{2} = m \quad \text{(mean)}$
- $\det \left( \begin{bmatrix} a & b \\ c & d \end{bmatrix} \right) = ad - bc = \lambda_1 \lambda_2 = p \quad \text{(product)}$
-
-
- # Linear Algebra Notes: Subspaces, Projections, and Orthogonality (Fruit Analogy)
  
  ---
	- link : https://chatgpt.com/share/6876a36f-c0a0-800c-904a-0d8bab329f78
	- https://chatgpt.com/share/6876a36f-c0a0-800c-904a-0d8bab329f78
	-
	- ---
	- ## **Fundamental Subspaces (Fruit Analogy)**
	- ### Matrix Setup:
	- 5 Fruits (Items): Apple, Orange, Watermelon, Lemon, Cherry.
	- 5 Features: Sweetness, Sourness, Color\_Red, Size\_Small, Contains\_Seeds.
	  
	  Matrix $A$ (5x5):
	  
	  ```
	  A =
	  [7, 3, 1, 0, 1]  // Apple
	  [6, 4, 0, 0, 1]  // Orange
	  [8, 2, 1, 0, 1]  // Watermelon
	  [2, 9, 0, 1, 1]  // Lemon
	  [9, 1, 1, 1, 1]  // Cherry
	  ```
	  
	  Each row: a fruit (item).
	  Each column: a feature.
	  
	  ---
	- ### Subspaces:
	- **Row Space**: All combinations of fruit feature patterns.
	- **Column Space**: All possible feature combinations achievable using these fruits.
	- **Null Space**: Hypothetical fruit combinations that result in zero features (impossible in real life).
	- **Left Null Space**: Feature combinations that can never be achieved by any mixture of fruits (impossible feature demands).$A^TX=0$
	- ---
	- ## **Projection Matrix ($P$)**
	- **Purpose**: Projects any vector onto the **column space** of $A$.
	- when there is no definite solutions, we use approximations
	- **Formula:**
	  
	  $$
	  P = A (A^T A)^{-1} A^T
	  $$
	- **Usage:**
	  
	  $$
	  \text{Projected}\ b = P \cdot b
	  $$
	  
	  Where $b$ is your desired feature pattern (even if impossible).
	- **Interpretation:**
		- Projects impossible feature requests onto achievable combinations.
		- Gives the **closest possible feature vector** within column space.
	- **Error Vector:**
	  
	  $$
	  \text{Error} = b - P \cdot b
	  $$
	- This error is orthogonal to the column space (lies in the left null space).
	  
	  ---
	- ## **Orthogonal Matrix ($Q$)**
	- **Definition:**
	  
	  $$
	  Q^T Q = I
	  $$
	- **Properties:**
		- Represents pure rotations/reflections.
		- Preserves vector lengths and angles.
		- Used in **QR decomposition**.
	- **QR Decomposition:**
	  
	  $$
	  A = Q \cdot R
	  $$
	- **Solving $A \cdot x = b$ using QR:**
	  
	  $$
	  Q \cdot R \cdot x = b
	  $$
	  Multiply by $Q^T$:
	  $$
	  R \cdot x = Q^T \cdot b
	  $$
	  Solve using back substitution (as $R$ is triangular).
	- **Intuition:**
		- $Q$ rotates the system into an easier-to-solve basis.
		  
		  ---
	- ## **Key Conceptual Insights:**
	- If your **target feature pattern ($b$)** is not in column space, projection matrix provides the **best possible achievable result**.
	- The leftover part of your request lies in the **left null space** — mathematically orthogonal to your dataset's output space.
	- Adding a **new fruit (feature vector)** expands the column space — unlocking new directions to reach previously impossible feature combinations.
	  
	  
	  ---
	- ## **Projection Matrix Properties**
	  
	  | Property                              | True/False |
	  |---------------------------------------|------------|
	  | Symmetric                             | True       |
	  | Orthogonal                            | False      |
	  | Orthogonally Diagonalizable           | True       |
	  | Always Rank 1                         | False      |
	- **Symmetric**: $P^T = P$.
	- **Orthogonal**: No (doesn't preserve lengths).
	- **Orthogonally Diagonalizable**: Yes (all symmetric matrices are).
	- **Rank 1**: No (rank equals dimension of projected subspace).
	  
	  ---
	- ## **Doubts Highlighted:**
	- Why projection matrix isn't orthogonal? (Because it doesn't preserve lengths; it 'flattens' vectors onto a subspace.)
	- Left null space significance? (Captures the impossible feature demands.)
	- When can projection matrix be rank 1? (Only when projecting onto a line — not general.)
	  
	  ---
	- ## **Key Formulas:**
	- **Projection Matrix:**
	  
	  $$
	  P = A (A^T A)^{-1} A^T
	  $$
	- **Orthogonal Matrix Condition:**
	  
	  $$
	  Q^T Q = I
	  $$
	- **QR Decomposition:**
	  
	  $$
	  A = Q \cdot R
	  $$
	- **Projection of b:**
	  
	  $$
	  \text{Projected}\ b = P \cdot b
	  $$
	- **Error Vector:**
	  
	  $$
	  b - P \cdot b
	  $$
	  
	  
	  ---
-
- All orthogonal vectors are linear independent but not vice versa
- orthogonal vectors lies in the same subspace but perpendicular to each other
- basis not always in standard form,lets assume a tilted plane in $3^d$ which cant have standard basis it may have numbers as X is increasing 2 times the Y.
- Eigen decomposition make easier matrix power computation. as we only calculates $D^n$
	- $A^n = P D^n P^{-1}$
	-
	-
	-
- complex matrices : two dimensional represesntation of each element in vector
- A **Hermitian matrix** is a complex square matrix that is equal to its own **conjugate transpose**.
  In simple terms:
  $A=\overline{A}^T$
	- For real matrices, Hermitian matrices are just **symmetric matrices**.
	  
	  ---
	- ### Properties of Hermitian Matrices:
	- **Diagonal elements** are always **real numbers**.
	- **Eigenvalues** of Hermitian matrices are **always real**.
	- Eigenvectors of Hermitian matrices corresponding to different eigenvalues are **orthogonal**.
-
- dot product   === innerproduct
- $A^TA    = AA^T       === \overline{A}^TA = A\overline{A}^T = I$
-
-
-
- think conjugates as reflections along axis
- orthogonal matrix === unitary matrix
	- ### Why are they important?
	- **Preserve length and angles** (like rotations in space).
	- Used in **quantum computing**, **signal processing**, and **machine learning**.
	- Think of them as "complex-number rotation matrices."
-
- ## week 6:SVD & POSITIVE DEFINATE MATRICES
	- ### Spectral decompositon
		- Matrix can do rotation,stretching to symmetric matrices.some matrices are simple which just participate in single rotation but some we cant visualize as they are composite of different rotates and stretches.
		- spectral decomposition unpacks these composite matrces into matrices that first rotates stretch and then rotate  $S = Q \Lambda Q^{\mathrm{T}}$
			-
			- The columns of **Q** are the **eigenvectors** of  S, and they are orthonormal (i.e., they have unit length and are mutually perpendicular).
			-
			- Geometrically, **Q** represents a **rotation** (or reflection) in the coordinate system. It aligns the coordinate axes with the directions of the eigenvectors of S .
			-
			- **Q^T** is the transpose of **Q**, so its rows are the eigenvectors of S.
			-
			- Geometrically, $Q^T$ represents the **inverse rotation** (or reflection) that brings the coordinate system back to its original orientation after the stretching operation.
			-
			- **Diagonal Matrix**:
			- $\Lambda$ is a diagonal matrix containing the **eigenvalues** of S along its diagonal.
			- It has eigen values as diagonal values others zero entries
			-
			-
			-
			-
		-
	- ### SVD:
		- ![image.png](../assets/image_1753006008955_0.png)
		-
		- one decomposition rules all other decompositions ,because it can be applied to any matrix,even rectangular matricx.
		- ![image.png](../assets/image_1753088428313_0.png)
		- $M = U \cdot \Sigma \cdot V^*$
		- where $U$ contain the normalized orthognal eigen vectors(for normal rotation) of $MM^T$ corresponding to eigenvalues(sorted for low rank approximation) in diagonal matrix. and $\Sigma$ is diagonal matrix that stretches or squishes the object and then $V^*$ to rotate back.orthogonal vectors acts as axes in rotation.
		- Singular value decomposition is a method that unpacks any matrix as
			-
-
-
-
- ## Quiz1
	-
-