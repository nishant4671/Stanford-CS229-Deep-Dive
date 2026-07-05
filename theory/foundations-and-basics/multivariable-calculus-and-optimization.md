# Multivariable Calculus & Optimization Foundations

## 1️⃣ Partial Derivatives & Gradient

- **Partial derivative** of a scalar function \(f:\mathbb{R}^d \to \mathbb{R}\) with respect to the \(i\)-th coordinate:
  $$\frac{\partial f}{\partial x_i}(\mathbf{x}) = \lim_{h\to0}\frac{f(x_1,\dots,x_i+h,\dots,x_d)-f(\mathbf{x})}{h}$$
- **Gradient** \(\nabla f(\mathbf{x})\) stacks all partials into a column vector:
  $$\nabla f(\mathbf{x}) = \begin{bmatrix}\frac{\partial f}{\partial x_1} \\ \frac{\partial f}{\partial x_2} \\ \vdots \\ \frac{\partial f}{\partial x_d}\end{bmatrix}\in\mathbb{R}^d$$
  - Geometric meaning: direction of steepest ascent; the negative gradient points to steepest descent.

## 2️⃣ Hessian Matrix (Second‑Order Derivatives)

- **Hessian** of \(f\) is the matrix of second partial derivatives:
  $$\mathbf{H}_f(\mathbf{x}) = \begin{bmatrix}\frac{\partial^2 f}{\partial x_1^2} & \frac{\partial^2 f}{\partial x_1\partial x_2} & \dots \\
  \frac{\partial^2 f}{\partial x_2\partial x_1} & \frac{\partial^2 f}{\partial x_2^2} & \dots \\
  \vdots & \vdots & \ddots\end{bmatrix}$$
- For twice‑differentiable \(f\), the Hessian is symmetric (\(\frac{\partial^2 f}{\partial x_i\partial x_j}=\frac{\partial^2 f}{\partial x_j\partial x_i}\)).
- **Positive‑definite Hessian** \(\mathbf{H}\succ0\) ⇔ \(f\) is locally *strictly convex* around that point.

## 3️⃣ Chain Rule (Multivariate)

If \(\mathbf{z}=g(\mathbf{x})\) with \(g:\mathbb{R}^n\to\mathbb{R}^m\) and \(f:\mathbb{R}^m\to\mathbb{R}\), then
$$\nabla_{\mathbf{x}} (f\circ g)(\mathbf{x}) = \mathbf{J}_g(\mathbf{x})^{\top}\,\nabla_{\mathbf{z}} f(g(\mathbf{x}))$$
where \(\mathbf{J}_g\) is the Jacobian matrix of \(g\) (\(m\times n\)).

## 4️⃣ Taylor Expansion (Second Order)

For a smooth \(f\) around \(\mathbf{x}_0\):
$$f(\mathbf{x}) \approx f(\mathbf{x}_0) + \nabla f(\mathbf{x}_0)^{\top}(\mathbf{x}-\mathbf{x}_0) + \frac{1}{2}(\mathbf{x}-\mathbf{x}_0)^{\top}\mathbf{H}_f(\mathbf{x}_0)(\mathbf{x}-\mathbf{x}_0)$$
Useful for deriving Newton's method.

## 5️⃣ Convex Functions & Sets

- **Convex set** \(S\): for any \(\mathbf{x},\mathbf{y}\in S\) and \(\lambda\in[0,1]\), \(\lambda\mathbf{x}+(1-\lambda)\mathbf{y}\in S\).
- **Convex function** \(f\) on a convex set \(S\):
  $$f(\lambda\mathbf{x}+(1-\lambda)\mathbf{y}) \le \lambda f(\mathbf{x}) + (1-\lambda)f(\mathbf{y})$$
- **First‑order condition** (if differentiable):
  $$f(\mathbf{y}) \ge f(\mathbf{x}) + \nabla f(\mathbf{x})^{\top}(\mathbf{y}-\mathbf{x})$$
- **Second‑order condition**: \(\mathbf{H}_f(\mathbf{x})\succeq 0\) for all \(\mathbf{x}\) ⇔ \(f\) is convex.

## 6️⃣ Optimization Algorithms (Core for ML)

### 6.1 Gradient Descent (GD)
```text
Initialize w_0
repeat:
    w_{t+1} = w_t - \alpha \nabla L(w_t)
until convergence
```
- \(\alpha\) – learning rate (step size).
- Converges to a *local* minimum for non‑convex \(L\); to the *global* minimum for convex \(L\).

### 6.2 Stochastic Gradient Descent (SGD)
Replace full gradient with a mini‑batch estimate:
$$w_{t+1}=w_t-\alpha\,\widehat{\nabla L}(w_t)$$
Reduces per‑iteration cost; introduces noise that can help escape shallow local minima.

### 6.3 Newton's Method (Second‑Order)
```text
w_{t+1}= w_t - \mathbf{H}_L(w_t)^{-1}\,\nabla L(w_t)
```
- Uses Hessian inverse → faster local convergence (quadratic) but costly to compute/invert.
- Practical variant: *Quasi‑Newton* (e.g., BFGS, L‑BFGS) approximates Hessian.

### 6.4 Lagrange Multipliers (Constrained Optimization)
For problem \(\min_{\mathbf{x}} f(\mathbf{x})\) subject to \(g_i(\mathbf{x})=0\):
$$\mathcal{L}(\mathbf{x},\lambda)= f(\mathbf{x}) + \sum_i \lambda_i g_i(\mathbf{x})$$
Stationarity conditions:
$$\nabla_{\mathbf{x}} \mathcal{L}=0,\quad g_i(\mathbf{x})=0$$
KKT conditions extend to inequality constraints.

## 7️⃣ Quick Checklist for Calculus & Optimization

- [ ] Partial derivatives and gradient notation
- [ ] Hessian matrix properties (symmetry, PD ⇒ convexity)
- [ ] Multivariate chain rule and Jacobian
- [ ] Second‑order Taylor expansion
- [ ] Convex sets/functions, first‑ and second‑order conditions
- [ ] Gradient descent & stochastic variants
- [ ] Newton / quasi‑Newton methods
- [ ] Lagrange multipliers & KKT conditions

---

*All formulas are in LaTeX for easy copy‑paste into Jupyter notebooks.*
