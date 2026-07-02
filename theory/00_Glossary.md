# CS229 Glossary

> Add new terms here as you encounter them. Organized by topic area.

---

## General Machine Learning

* **Supervised Learning**: Learning from labeled data $(x^{(i)}, y^{(i)})$ to predict outputs for new inputs.
* **Unsupervised Learning**: Finding hidden structure in unlabeled data (no $y$ labels).
* **Reinforcement Learning**: An agent learns to make decisions by receiving rewards/penalties from an environment.
* **Training Set**: The dataset used to train the model. Denoted as $\{(x^{(i)}, y^{(i)}); i=1,...,m\}$.
* **Hypothesis**: The function $h_\theta(x)$ that maps inputs to predicted outputs.
* **Cost Function / Loss Function**: A function $J(\theta)$ that measures how wrong the model's predictions are.
* **Overfitting**: Model fits training data too closely (including noise), failing to generalize.
* **Underfitting**: Model is too simple to capture the underlying pattern in the data.
* **Feature**: An individual measurable property of the data (a column in $X$).
* **Label / Target**: The output variable $y$ we are trying to predict.

## Linear Algebra Essentials

* **Vector**: An ordered list of numbers, e.g., $x \in \mathbb{R}^n$.
* **Matrix**: A 2D array of numbers, e.g., $X \in \mathbb{R}^{m \times n}$.
* **Transpose**: Flipping rows and columns: $(A^T)_{ij} = A_{ji}$.
* **Dot Product**: $a \cdot b = \sum_i a_i b_i$. Measures similarity between vectors.
* **Eigenvalue / Eigenvector**: $Av = \lambda v$ — directions that don't change under transformation $A$.
* **Positive Definite Matrix**: A symmetric matrix where $x^TAx > 0$ for all non-zero $x$.

## Optimization

* **Gradient Descent**: Iteratively update parameters: $\theta := \theta - \alpha \nabla J(\theta)$.
* **Learning Rate ($\alpha$)**: Step size for gradient descent. Too large = diverge, too small = slow.
* **Batch Gradient Descent**: Uses the *entire* training set for each update.
* **Stochastic Gradient Descent (SGD)**: Uses *one* random sample per update. Faster but noisier.
* **Mini-Batch GD**: Uses a small batch of samples per update. Best of both worlds.
* **Convergence**: When $J(\theta)$ stops changing significantly between iterations.
* **Convex Function**: A function where any local minimum is also a global minimum (bowl-shaped).

## Probability & Statistics

* **Bayes' Rule**: $P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)}$
* **Likelihood**: $L(\theta) = P(\text{data} | \theta)$ — probability of observing the data given the parameters.
* **Maximum Likelihood Estimation (MLE)**: Choose $\theta$ that maximizes $L(\theta)$.
* **MAP (Maximum A Posteriori)**: Like MLE but includes a prior: $\theta_{MAP} = \arg\max P(\theta | \text{data})$.
* **Gaussian Distribution**: $\mathcal{N}(\mu, \sigma^2)$ — the bell curve. Defined by mean $\mu$ and variance $\sigma^2$.
* **Bernoulli Distribution**: $P(y=1) = \phi$, $P(y=0) = 1 - \phi$. For binary outcomes.

## Supervised Learning Algorithms

* **Normal Equation**: Closed-form solution for linear regression: $\theta = (X^TX)^{-1}X^Ty$.
* **Sigmoid Function**: $\sigma(z) = \frac{1}{1 + e^{-z}}$. Maps any real number to $(0, 1)$.
* **Logistic Regression**: Classification using sigmoid: $h_\theta(x) = \sigma(\theta^Tx)$.
* **Generalized Linear Model (GLM)**: A framework unifying linear/logistic/softmax regression via the exponential family.
* **GDA (Gaussian Discriminant Analysis)**: A generative model that assumes class-conditional Gaussians.
* **Naive Bayes**: Assumes features are conditionally independent given the class label.
* **SVM (Support Vector Machine)**: Finds the maximum-margin hyperplane separating classes.
* **Kernel**: A function $K(x, z)$ that computes dot products in high-dimensional space without explicitly transforming.
* **Backpropagation**: Algorithm for computing gradients in neural networks via the chain rule.

## Learning Theory

* **Bias**: Error from overly simplistic model assumptions (underfitting).
* **Variance**: Error from sensitivity to small fluctuations in the training set (overfitting).
* **Regularization**: Adding a penalty term to $J(\theta)$ to prevent overfitting (e.g., $\lambda||\theta||^2$).
* **VC Dimension**: The largest set of points a model can shatter (perfectly classify in all arrangements).

## Unsupervised Learning

* **K-Means**: Iterative clustering: assign points to nearest centroid, then update centroids.
* **EM Algorithm**: Iteratively performs E-step (estimate hidden variables) and M-step (update parameters).
* **PCA (Principal Components Analysis)**: Projects data onto directions of maximum variance.
* **ICA (Independent Components Analysis)**: Finds statistically independent components (e.g., cocktail party problem).

## Reinforcement Learning

* **MDP (Markov Decision Process)**: Framework defined by $(S, A, P, R, \gamma)$ — states, actions, transitions, rewards, discount.
* **Policy ($\pi$)**: A mapping from states to actions: $\pi(s) = a$.
* **Value Function $V^\pi(s)$**: Expected cumulative reward starting from state $s$ under policy $\pi$.
* **Q-Function $Q(s,a)$**: Expected cumulative reward taking action $a$ in state $s$, then following optimal policy.
* **Bellman Equation**: $V^\pi(s) = R(s) + \gamma \sum_{s'} P(s'|s, \pi(s)) V^\pi(s')$.
