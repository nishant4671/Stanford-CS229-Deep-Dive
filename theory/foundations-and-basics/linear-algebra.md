# Linear Algebra Foundations

## 1️⃣ Vectors & Vector Operations

- **Definition**: A vector \(\mathbf{x} \in \mathbb{R}^n\) is an ordered list of \(n\) real numbers, usually written as a column:
  $$\mathbf{x}=\begin{bmatrix}x_1\\ x_2\\ \vdots\\ x_n\end{bmatrix}$$
- **Norms** (lengths):
  - \(\ell_2\) norm: \(\|\mathbf{x}\|_2 = \sqrt{\sum_{i=1}^n x_i^2}\)
  - \(\ell_1\) norm: \(\|\mathbf{x}\|_1 = \sum_{i=1}^n |x_i|\)
- **Dot (inner) product**:
  $$\mathbf{u}^\top \mathbf{v}=\sum_{i=1}^n u_i v_i$$
  - Gives the cosine of the angle between two vectors: \(\cos\theta = \frac{\mathbf{u}^\top \mathbf{v}}{\|\mathbf{u}\|\|\mathbf{v}\|}\)

## 2️⃣ Matrices & Basic Operations

- **Matrix** \(\mathbf{A} \in \mathbb{R}^{m\times n}\) is a rectangular array of numbers.
- **Transpose**: \(\mathbf{A}^\top\) flips rows ↔ columns.
- **Matrix multiplication** (\(\mathbf{C}=\mathbf{A}\mathbf{B}\))
  - If \(\mathbf{A}\) is \(m\times k\) and \(\mathbf{B}\) is \(k\times n\), then \(\mathbf{C}\) is \(m\times n\).
  - Entry formula: \(c_{ij}=\sum_{\ell=1}^k a_{i\ell}b_{\ell j}\).
- **Identity matrix** \(\mathbf{I}_n\): 1 on the diagonal, 0 elsewhere. \(\mathbf{AI}=\mathbf{A}\).
- **Inverse** (if it exists): \(\mathbf{A}^{-1}\) s.t. \(\mathbf{AA}^{-1}=\mathbf{I}\). Only square, full‑rank matrices are invertible.
- **Determinant** \(\det(\mathbf{A})\): scalar describing volume scaling. Useful for checking invertibility (\(\det \neq 0\)).

## 3️⃣ Special Matrices

| Type | Definition | Key Property |
|------|------------|--------------|
| Symmetric | \(\mathbf{A}=\mathbf{A}^\top\) | Eigenvalues are real, orthogonal eigenvectors |
| Orthogonal | \(\mathbf{Q}\mathbf{Q}^\top=\mathbf{I}\) | Preserves length: \(\|\mathbf{Qx}\|=\|\mathbf{x}\|\) |
| Positive‑definite | \(\mathbf{x}^\top\mathbf{A}\mathbf{x}>0\;\forall\;\mathbf{x}\neq0\) | All eigenvalues > 0 |

## 4️⃣ Eigen‑Decomposition & SVD

- **Eigenvalues / Eigenvectors**: \(\mathbf{A}\mathbf{v}=\lambda\mathbf{v}\).
  - For symmetric \(\mathbf{A}\): \(\mathbf{A}=\mathbf{Q}\Lambda\mathbf{Q}^\top\) where \(\mathbf{Q}\) orthogonal, \(\Lambda\) diagonal of eigenvalues.
- **Singular Value Decomposition (SVD)**:
  $$\mathbf{A}=\mathbf{U}\Sigma\mathbf{V}^\top$$
  - \(\mathbf{U}\) (\(m\times m\)) and \(\mathbf{V}\) (\(n\times n\)) are orthogonal, \(\Sigma\) diagonal with non‑negative singular values.
  - Useful for low‑rank approximations and pseudo‑inverse.

## 5️⃣ Matrix Calculus (Gradients)

When optimizing a loss \(L(\mathbf{w})\) we need \(\nabla_{\mathbf{w}} L\).

- **Gradient of a quadratic form**:
  $$\frac{\partial}{\partial\mathbf{x}}\bigl(\mathbf{x}^\top\mathbf{A}\mathbf{x}\bigr)=\bigl(\mathbf{A}+\mathbf{A}^\top\bigr)\mathbf{x}$$
  - For symmetric \(\mathbf{A}\): \(2\mathbf{A}\mathbf{x}\).
- **Gradient of a linear term**:
  $$\frac{\partial}{\partial\mathbf{x}}\bigl(\mathbf{b}^\top\mathbf{x}\bigr)=\mathbf{b}$$
- **Trace tricks** (very handy):
  $$\frac{\partial}{\partial\mathbf{X}}\operatorname{tr}(\mathbf{AX}) = \mathbf{A}^\top$$
  $$\frac{\partial}{\partial\mathbf{X}}\operatorname{tr}(\mathbf{X}^\top\mathbf{A}\mathbf{X}) = (\mathbf{A}+\mathbf{A}^\top)\mathbf{X}$$

### 📚 Quick Checklist for Linear‑Algebra Review

- [ ] Vector notation, norms, dot product, cosine similarity
- [ ] Matrix shapes, transpose, multiplication rules
- [ ] Identity, inverse, determinant
- [ ] Eigen‑decomposition, SVD
- [ ] Basic matrix calculus identities (gradients of quadratic/linear forms, trace tricks)

---

*All formulas are written in LaTeX for easy copy‑paste into Jupyter notebooks.*
