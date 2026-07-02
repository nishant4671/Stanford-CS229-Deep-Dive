# Step 0: Mathematical Foundations for CS229

This document contains our structured, detailed notes for the linear algebra and calculus concepts required to understand machine learning algorithms.

---

## Lesson 0.1: Vectors, Matrices, and Dimension Alignment

In machine learning, we group data together into arrays. Understanding their shapes and how they interact is 90% of the battle.

### 1. Vectors (1D Arrays)
A vector is an ordered list of numbers. 
* Mathematically, we write a vector $\vec{x}$ (or bold $\mathbf{x}$) as a column:
  $$x = \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix}$$
* This vector belongs to $n$-dimensional space, written as $x \in \mathbb{R}^n$.
* **Intuition:** Think of a vector as a single data point's features. For example, if we are predicting house prices, $x = \begin{bmatrix} 2000 \\ 3 \end{bmatrix}$ where $2000$ is square footage and $3$ is the number of bedrooms.

### 2. Matrices (2D Arrays)
A matrix is a grid of numbers.
* A matrix $A \in \mathbb{R}^{m \times n}$ has $m$ rows and $n$ columns.
* **Intuition:** Think of a matrix as a *collection* of data points.
  * Each **row** is a different house (data point).
  * Each **column** is a different feature (size, bedrooms).

### 3. The Transpose Operator ($T$)
Transposing flips a matrix or vector over its diagonal. It turns rows into columns and columns into rows.
* If $x = \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}$ (a column vector of size $3 \times 1$), then:
  $$x^T = \begin{bmatrix} 1 & 2 & 3 \end{bmatrix} \quad \text{(a row vector of size } 1 \times 3\text{)}$$
* For a matrix:
  $$\begin{bmatrix} 1 & 2 \\ 3 & 4 \\ 5 & 6 \end{bmatrix}^T = \begin{bmatrix} 1 & 3 & 5 \\ 2 & 4 & 6 \end{bmatrix}$$

---

## Lesson 0.2: Matrix Multiplication & The Dot Product

When multiplying two matrices (or vectors), we must follow one golden rule: **The dimensions must align.**

### 1. Vector-Vector Multiplication (The Dot Product)
To multiply two vectors, we transpose the first one to make it a row, and keep the second as a column.
If $u, v \in \mathbb{R}^n$:
$$u^T v = \begin{bmatrix} u_1 & u_2 & \dots & u_n \end{bmatrix} \begin{bmatrix} v_1 \\ v_2 \\ \vdots \\ v_n \end{bmatrix} = u_1v_1 + u_2v_2 + \dots + u_nv_n$$
* **Dimensions:** $(1 \times n) \times (n \times 1) = (1 \times 1)$ (a single scalar number).
* **NumPy:** In Python, this is `u @ v` or `np.dot(u, v)`.

### 2. Matrix-Matrix Multiplication
If you multiply matrix $A$ by matrix $B$ ($C = AB$):
* $A$ must have shape $m \times \mathbf{k}$
* $B$ must have shape $\mathbf{k} \times n$
* **The inner dimensions must match ($\mathbf{k}$)**.
* The resulting matrix $C$ will have the shape of the outer dimensions: $m \times n$.

**How it's calculated:** Each entry $C_{ij}$ is the dot product of Row $i$ of matrix $A$ and Column $j$ of matrix $B$.

---

## ✏️ Checkpoint 0.1: Quick Practice

Let's test this dimension alignment rule. 

Suppose we have:
* A matrix $X$ of shape $100 \times 3$ (representing 100 data points, each with 3 features).
* A column vector of weights $\theta$ of shape $3 \times 1$ (representing the weight/importance of each of the 3 features).

**Question:** 
1. Can we compute $X\theta$? If so, what will be the shape of the resulting array?
2. Can we compute $\theta X$? Why or why not?
