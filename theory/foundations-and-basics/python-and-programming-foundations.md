# Python & Programming Foundations

## 1️⃣ Python Basics

- **Data Types**: `int`, `float`, `bool`, `str`, `list`, `tuple`, `dict`, `set`.
- **Control Flow**:
  ```python
  if condition:
      # do something
  elif other_condition:
      # do something else
  else:
      # fallback
  
  for item in iterable:
      # loop body
  
  while condition:
      # loop body
  ```
- **Functions**:
  ```python
  def func_name(arg1, arg2=default):
      """Docstring – describe purpose, args, returns"""
      # body
      return result
  ```
  - First‑class objects, closures, default arguments.
- **List Comprehensions** for concise vectorized‑style operations:
  ```python
  squares = [x**2 for x in range(10)]
  ```
- **Exception Handling**:
  ```python
  try:
      risky_operation()
  except SomeError as e:
      handle(e)
  finally:
      cleanup()
  ```

## 2️⃣ NumPy – Core Numerical Library

- **Arrays**: `np.array([...])`, shape, dtype.
- **Vectorized Operations** (no explicit Python loops):
  ```python
  X = np.random.randn(100, 3)   # 100 samples, 3 features
  theta = np.array([0.1, 0.2, 0.3])
  y_pred = X @ theta            # matrix‑vector multiplication
  ```
- **Broadcasting**: automatic expansion of dimensions for element‑wise ops.
- **Linear Algebra helpers**:
  - `np.linalg.inv(A)`, `np.linalg.solve(A, b)`, `np.linalg.eig(A)`, `np.linalg.svd(A)`.
- **Statistical utilities**: `np.mean`, `np.var`, `np.std`, `np.cov`.

## 3️⃣ Pandas – Data Manipulation & Exploration

- **Series** (1‑D) and **DataFrame** (2‑D) objects.
- **Loading data**:
  ```python
  df = pd.read_csv('data.csv')
  ```
- **Basic ops**: `df.head()`, `df.describe()`, column selection `df['col']`, filtering `df[df['age'] > 30]`.
- **Group‑by / aggregation**:
  ```python
  df.groupby('category').mean()
  ```
- **Missing data handling**: `df.isnull().sum()`, `df.fillna(0)`, `df.dropna()`.

## 4️⃣ Visualization (Matplotlib & Seaborn)

- **Matplotlib** basics:
  ```python
  import matplotlib.pyplot as plt
  plt.scatter(X[:,0], X[:,1], c=y)
  plt.xlabel('Feature 1')
  plt.ylabel('Feature 2')
  plt.title('Scatter plot of two features')
  plt.show()
  ```
- **Seaborn** for statistical plots:
  ```python
  import seaborn as sns
  sns.regplot(x='feature1', y='target', data=df)
  ```

## 5️⃣ Software Engineering Practices for ML Projects

| Practice | Why it matters | Quick tip |
|----------|----------------|----------|
| **Version control (git)** | Reproducibility, collaboration | `git init`, branch per experiment, commit often |
| **Virtual environments** | Isolate dependencies | `python -m venv env` → `source env/bin/activate` |
| **Requirements file** | Pin exact package versions | `pip freeze > requirements.txt` |
| **Modular code** | Easier testing & reuse | Separate data loading, model, training, utils |
| **Unit testing** | Catch bugs early | `pytest` with small synthetic datasets |
| **Logging** | Track experiments | `logging` module or tools like `mlflow` |

## 6️⃣ Quick Checklist for Python Foundations

- [ ] Understand basic data types and control flow
- [ ] Write clean functions with docstrings
- [ ] Perform vectorized NumPy operations without loops
- [ ] Load, explore, and preprocess data with pandas
- [ ] Visualize data using matplotlib/seaborn
- [ ] Set up a git repo, virtual env, and `requirements.txt`
- [ ] Write at least one unit test for a helper function

---

*All code snippets are ready to copy‑paste into a Jupyter notebook.*
