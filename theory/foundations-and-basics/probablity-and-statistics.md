# Probability and Statistics Foundations

## 1️⃣ Basic Probability Concepts

- **Sample Space** \(\Omega\): the set of all possible outcomes of an experiment.
- **Event** \(A \subseteq \Omega\): a subset of outcomes.
- **Probability Measure** \(P\):
  - Non‑negative: \(P(A) \ge 0\)
  - Normalized: \(P(\Omega) = 1\)
  - Additive: for disjoint \(A,B\), \(P(A\cup B) = P(A)+P(B)\)
- **Conditional Probability**:
  $$P(A\mid B)=\frac{P(A\cap B)}{P(B)}\quad\text{(if }P(B)>0\text{)}$$
- **Law of Total Probability**:
  $$P(A)=\sum_i P(A\mid B_i)P(B_i)$$ for a partition \(\{B_i\}\) of \(\Omega\).
- **Bayes' Theorem** (the workhorse of Bayesian inference):
  $$P(A\mid B)=\frac{P(B\mid A)P(A)}{P(B)}$$

## 2️⃣ Random Variables

- **Discrete RV** \(X\): takes values in a countable set. Described by a **probability mass function** (PMF) \(p_X(x)=P(X=x)\).
- **Continuous RV** \(X\): takes values in an interval. Described by a **probability density function** (PDF) \(f_X(x)\) where \(P(a\le X\le b)=\int_a^b f_X(x)\,dx\).
- **Cumulative Distribution Function (CDF)**:
  $$F_X(x)=P(X\le x)$$
  Works for both discrete and continuous RVs.
- **Expectation (Mean)**:
  - Discrete: \(\mathbb{E}[X]=\sum_x x\,p_X(x)\)
  - Continuous: \(\mathbb{E}[X]=\int_{-\infty}^{\infty} x\,f_X(x)\,dx\)
- **Variance**:
  $$\operatorname{Var}(X)=\mathbb{E}\big[(X-\mathbb{E}[X])^2\big]=\mathbb{E}[X^2]-\big(\mathbb{E}[X]\big)^2$$
- **Covariance** and **Correlation** for two RVs \(X,Y\):
  $$\operatorname{Cov}(X,Y)=\mathbb{E}[XY]-\mathbb{E}[X]\mathbb{E}[Y]$$
  $$\rho_{XY}=\frac{\operatorname{Cov}(X,Y)}{\sigma_X\sigma_Y}$$

## 3️⃣ Common Distributions (used in ML)

| Distribution | Type | PDF/PMF | Typical Use |
|--------------|------|---------|-------------|
| **Bernoulli** | Discrete | $p^x(1-p)^{1-x}$ for $x\in\{0,1\}$ | Binary classification label
| **Binomial** | Discrete | $\binom{n}{k}p^k(1-p)^{n-k}$ | Sum of independent Bernoulli trials
| **Gaussian (Normal)** | Continuous | $\frac{1}{\sqrt{2\pi\sigma^2}}\exp\!\bigl(-\frac{(x-\mu)^2}{2\sigma^2}\bigr)$ | Many ML models assume Gaussian noise
| **Multivariate Gaussian** | Continuous | $\frac{1}{(2\pi)^{d/2}|\Sigma|^{1/2}}\exp\bigl(-\tfrac12 (x-\mu)^\top\Sigma^{-1}(x-\mu)\bigr)$ | Linear regression, LDA, GP priors
| **Poisson** | Discrete | $\frac{\lambda^k e^{-\lambda}}{k!}$ | Count data (e.g., event arrivals)

## 4️⃣ Statistical Estimation

- **Maximum Likelihood Estimation (MLE)**:
  $$\hat{\theta}_{\text{MLE}} = \arg\max_{\theta}\;\prod_{i=1}^n p_{X}(x_i\mid\theta)$$
  Often easier to maximize the log‑likelihood:
  $$\ell(\theta)=\sum_{i=1}^n \log p_{X}(x_i\mid\theta)$$
- **Maximum A Posteriori (MAP)** (adds a prior \(p(\theta)\)):
  $$\hat{\theta}_{\text{MAP}} = \arg\max_{\theta}\; \log p(\theta) + \sum_{i=1}^n \log p_{X}(x_i\mid\theta)$$
- **Bias‑Variance Decomposition** for an estimator \(\hat{f}(x)\):
  $$\mathbb{E}\big[(\hat{f}(x)-f(x))^2\big] = \underbrace{\big(\mathbb{E}[\hat{f}(x)]-f(x)\big)^2}_{\text{Bias}^2} + \underbrace{\mathbb{E}\big[(\hat{f}(x)-\mathbb{E}[\hat{f}(x)])^2\big]}_{\text{Variance}} + \sigma^2_{\text{noise}}$$

## 5️⃣ Quick Checklist for Probability/Statistics Review

- [ ] Sample space, events, probability axioms
- [ ] Conditional probability and Bayes' theorem
- [ ] Random variables, PMF/PDF, CDF, expectation, variance
- [ ] Common distributions (Bernoulli, Gaussian, etc.)
- [ ] MLE and MAP estimators
- [ ] Bias‑variance trade‑off

---

*All formulas are rendered in LaTeX for easy copy‑paste into notebooks.*
