# ✅ Numpy Complete Notes (Professional)

## 1. 📦 Importing Numpy


import numpy as np
 # Import numpy and create alias 'np'


---

## 2. 🎯 Creating Arrays
 ✅ From List to Array

```
# Create numpy array from list
np.array([1, 2, 3, 4, 5])
# Output: array([1, 2, 3, 4, 5])
```

### ✅ Array with Multiple Data Types

```python
# When multiple data types are present, all elements are converted to string
a = [1, 2, 3.5, "hello"]
np.array(a)
# Output: array(['1', '2', '3.5', 'hello'], dtype='<U32')
```

### ✅ 2D Array (Matrix)

```python
# Create a 2D array (matrix)
l = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
np.array(l)
```

---

## 3. 🛠️ Array Generating Functions

### 🔹 np.arange()

```python
# Generate a range of numbers
np.arange(1, 11)      # 1 to 10
np.arange(1, 11, 2)   # 1 to 10 with step 2
```

### 🔹 Zeros and Ones

```python
# Generate arrays filled with zeros and ones
np.zeros(6)               # 1D array of zeros
np.zeros((4, 8))          # 2D matrix of zeros
np.ones((4, 8))           # 2D matrix of ones
```

### 🔹 np.linspace()

```python
# Generate evenly spaced numbers
np.linspace(1, 5, 3)      # Generates [1. 3. 5.]
```

---

## 4. 🎲 Random Number Generators

### 🔹 Uniform Distribution (0 to 1)

```python
# Generate random numbers between 0 and 1
np.random.rand(5)
```

### 🔹 Standard Normal Distribution

```python
# Generate random numbers from standard normal distribution
np.random.randn(20)
```

### 🔹 Random Integers

```python
# Generate random integers within a range
np.random.randint(10, 20, 5)
```

---

## 5. 🔍 Array Attributes

```python
arr.shape    # Shape of the array
arr.size     # Total number of elements
arr.dtype    # Data type of array elements
```

---

## 6. 📊 Array Methods

```python
arr.min()             # Minimum value
arr.max()             # Maximum value
arr.sum()             # Sum of all elements
arr.sum(axis=0)       # Column-wise sum
arr.sum(axis=1)       # Row-wise sum
arr.mean()            # Mean of all elements
arr.std()             # Standard deviation
arr.argmax()          # Index of maximum value
```

---

## 7. 🔄 Reshaping Arrays

```python
# Reshape a 1D array into 2D matrix
arr = np.arange(1, 31).reshape(6, 5)
```

> 📌 **Note:** Reshaping only works if total elements remain the same.

---

## 8. ✂️ Indexing and Slicing

### 🔹 1D Array

```python
arr[6]         # Access single element
arr[3:5]       # Slice elements from index 3 to 4
```

### 🔹 2D Array

```python
arr[5]               # Entire 6th row
arr[0, 0]            # Element at row 0, column 0
arr[0:2, 1:3]        # Sub-matrix slice (rows 0-1, columns 1-2)
arr[:, 2]            # Entire 3rd column
```

---

## 9. ✅ Boolean Indexing

```python
# Select elements based on condition
arr = np.arange(11, 21)
bool_index = arr % 2 == 0
arr = arr[bool_index]     # Select only even numbers
```

---

## 10. ➗ Array Operations (Element-wise)

```python
# Basic operations between arrays
a1 + a2    # Addition
a1 - a2    # Subtraction
a1 * a2    # Multiplication
a1 / a2    # Division
a1 // a2   # Floor division
a1 ** a2   # Exponentiation
```

---

## 11. 🚀 Broadcasting

```python
# Operations on arrays with different shapes
arr = np.array([10, 20, 30, 40])
arr + 10   # Adds 10 to each element

arr2 = np.arange(1, 26).reshape(5, 5)
arr2 = arr2 + 10   # Adds 10 to each element in matrix
```

---

## 12. 🧩 Deep and Shallow Copy

### 🔹 Shallow Copy (View)

```python
# Shallow copy does not affect original array
a = np.arange(1, 21)
slice = a[:5] * 10
```

---

## 13. 🧮 Matrix Operations

### 🔹 Matrix Multiplication

```python
A @ B              # Matrix multiplication using '@'
np.dot(A, B)       # Matrix multiplication using np.dot()
```

### 🔹 Transpose

```python
A.T   # Transpose of matrix
```

---

## 14. 🏗️ Stacking Arrays

```python
np.vstack((a, b))           # Vertical stack
np.hstack((a, b))           # Horizontal stack
np.column_stack((a, b))     # Stack as columns
```

---

## 15. ✂️ Splitting Arrays

```python
np.hsplit(c, 4)     # Split horizontally into 4 parts
np.vsplit(c, 2)     # Split vertically into 2 parts
```

> 📌 **Note:** Number of splits must exactly divide array dimension.

---

## 16. 🎯 Practice Example: Valid Sudoku

```python
# Validate that sum of rows, columns, and 3x3 blocks is 45
for i in range(0, 9, 3):
    for j in range(0, 9, 3):
        print(s[i:i+3, j:j+3].sum())    # Each block sum must be 45
```

---

## 17. 🧑‍🎓 Student Dataset Example

### 🔹 Dataset

```python
data = np.array([
    [18, 85, 78],
    [19, 92, 88],
    [17, 76, 95],
    [18, 65, 70],
    [20, 90, 85]
])
```

### 🔹 Useful Operations

# Dataset properties
data.shape                       # Shape of the dataset
np.mean(data[:, 0])              # Average age

# Access specific columns
data[:, 1]                       # All Math Marks
np.max(data[:, 2])               # Highest Science Mark

# Conditional selection
data[data[:, 1] > 90]            # Students with Math Marks > 90

# Update operation
data[:, 1] = data[:, 1] + 5      # Increase Math Marks by 5

# Counting students
data[data[:, 0] < 19]            # Students younger than 19
len(data[data[:, 0] < 19])       # Number of students younger than 19

# Column-wise averages
np.mean(data, axis=0)            # Average marks in each subject

# Filter students with high scores
data[(data[:, 1] > 80) & (data[:, 2] > 80)]  # Students scoring >80 in both subjects

# Replace low Science Marks with 0
data[data[:, 2] < 75, 2] = 0


---



