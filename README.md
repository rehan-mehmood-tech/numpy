# NumPy Basics & Fundamentals

A clean, concise reference guide covering essential NumPy concepts, operations, and functions based on introductory practice code.

---

## 1. Introduction & Setup

**NumPy** (Numerical Python) is a powerful Python library used for numerical computations and handling multi-dimensional arrays efficiently.

### Installation
```bash
pip install numpy
```

---

## 2. Why NumPy over Python Lists?

Python lists perform **concatenation** when added together, whereas NumPy arrays perform **element-wise vector operations**.

```python
import numpy as np

# Python Lists (Concatenation)
list_a = [1, 2]
list_b = [3, 4]
print(list_a + list_b)  # Output: [1, 2, 3, 4]

# NumPy Arrays (Vectorized Addition)
arr_a = np.array([1, 2])
arr_b = np.array([3, 4])
print(arr_a + arr_b)    # Output: [4 6]
```

---

## 3. Array Creation Methods

```python
import numpy as np

# Basic Array
x = np.array([1, 2, 3, 4])

# Special Initialization Functions
zeros = np.zeros((4, 3))         # 4x3 matrix of zeros
ones = np.ones((4, 3))           # 4x3 matrix of ones
arange = np.arange(18)           # Array from 0 to 17
identity = np.eye(4)             # 4x4 Identity matrix
spaced = np.linspace(1, 10, 5)   # 5 evenly spaced numbers from 1 to 10
```

---

## 4. Random Array Generation

```python
# Uniform distribution [0.0, 1.0)
rand_arr = np.random.rand(3, 5)

# Standard Normal distribution (mean=0, stdev=1)
randn_arr = np.random.randn(4)

# Random integers between low (inclusive) and high (exclusive)
randint_arr = np.random.randint(5, 40, 10)
```

---

## 5. Array Properties & Attributes

```python
x = np.array([[1, 2, 3], [4, 5, 6]])

print(x.ndim)     # Output: 2 (Dimensions)
print(x.shape)    # Output: (2, 3)
print(x.dtype)    # Output: int64
print(len(x))     # Output: 2 (Length along first axis)

# Type Casting
float_arr = x.astype(float)
```

---

## 6. Basic Operations & Math

### Vectorized Arithmetic
```python
x = np.array([1, 2, 3, 4])

print(x * 2)   # Multiply each element by 2
print(x / 2)   # Divide each element by 2
print(x + 2)   # Add 2 to each element
print(x - 2)   # Subtract 2 from each element
```

### Mathematical Functions
```python
heights = np.array([1, 2, 3, 4])

print(np.min(heights))
print(np.max(heights))
print(np.sqrt(heights))
print(np.sin(heights))
print(np.cos(heights))
print(np.power(heights, 2))
```

---

## 7. Array Manipulation

### Append, Delete & Reshape
```python
arr = np.array([1, 2, 3, 4])

# Append
arr = np.append(arr, 5)            # [1, 2, 3, 4, 5]

# Delete by Index
arr = np.delete(arr, 2)            # Deletes element at index 2

# Reshape
reshaped = np.reshape(arr, (2, 2)) # Reshapes to 2x2 matrix
```

### Copy vs Reference
```python
# Reference Copy (Modifies original)
arr1 = np.array([1, 2, 3, 4])
arr2 = arr1
arr2[2] = 34  # arr1 is also modified!

# Deep Copy (Safe Copy)
arr1 = np.array([1, 2, 3, 4])
arr2 = arr1.copy()
arr2[2] = 34  # arr1 remains unchanged
```

---

## 8. Indexing, Slicing & Iteration

```python
arr = np.array([1, 2, 3, 4])

print(arr[2])     # 3 (Element at index 2)
print(arr[1:4])   # [2, 3, 4]
print(arr[::-1])  # [4, 3, 2, 1] (Reversed)

# Iteration
for val in arr:
    print(val)
```

---

## 9. Practice Exercises

### Exercise 1: Matrix Addition with Linspace
```python
# Create 2D arrays using linspace and calculate their sum
a = np.linspace(1, 100, 4).reshape(2, 2)
b = np.linspace(1, 100, 4).reshape(2, 2)

sum_matrix = a + b
print("Sum Matrix:\n", sum_matrix)
```

### Exercise 2: Statistical Analysis
```python
from scipy import stats

# Dataset of 1000 age values between 5 and 75
ages_in_pakistan = np.random.randint(5, 76, 1000)

mean_age = np.mean(ages_in_pakistan)
median_age = np.median(ages_in_pakistan)
mode_age = stats.mode(ages_in_pakistan, keepdims=True).mode[0]
std_dev = np.std(ages_in_pakistan)

print(f"Mean: {mean_age:.2f}")
print(f"Median: {median_age}")
print(f"Mode: {mode_age}")
print(f"Standard Deviation: {std_dev:.2f}")
```
