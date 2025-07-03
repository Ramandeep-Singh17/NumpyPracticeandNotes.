# ✅ Numpy Complete Notes

## 📚 Numpy Notes with Key Concepts and Codes

---

### 1. Importing Numpy

python
import numpy as np  # np is alias for numpy
2. Creating Arrays
From List to Array
python
Copy
Edit
np.array([1, 2, 3, 4, 5])
Output:

python
Copy
Edit
array([1, 2, 3, 4, 5])
Array with Multiple Data Types
python
Copy
Edit
a = [1, 2, 3.5, "hello"]
np.array(a)
Output (all converted to strings):

python
Copy
Edit
array(['1', '2', '3.5', 'hello'], dtype='<U32')
2D Array (Matrix)
python
Copy
Edit
l = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
np.array(l)
3. Array Generating Functions
np.arange()
python
Copy
Edit
np.arange(1, 11)      # 1 to 10
np.arange(1, 11, 2)   # 1 to 10 with step 2
Zeros and Ones
python
Copy
Edit
np.zeros(6)               # 1D array of zeros
np.zeros((4, 8))          # 2D matrix of zeros
np.ones((4, 8))           # 2D matrix of ones
np.linspace()
python
Copy
Edit
np.linspace(1, 5, 3)      # Evenly spaced numbers between 1 and 5
4. Random Number Generators
Uniform Distribution (0 to 1)
python
Copy
Edit
np.random.rand(5)         # Random numbers between 0 and 1
Standard Normal Distribution
python
Copy
Edit
np.random.randn(20)       # Random numbers roughly between -3 to +3
Random Integers
python
Copy
Edit
np.random.randint(10, 20, 5)  # Random integers between 10 and 20 (size 5)
5. Array Attributes
python
Copy
Edit
arr.shape    # Shape of the array
arr.size     # Total number of elements
arr.dtype    # Data type of array elements
6. Array Methods
python
Copy
Edit
arr.min()             # Minimum value
arr.max()             # Maximum value
arr.sum()             # Sum of all elements
arr.sum(axis=0)       # Column-wise sum
arr.sum(axis=1)       # Row-wise sum
arr.mean()            # Mean of all elements
arr.std()             # Standard deviation
arr.argmax()          # Index of maximum value
7. Reshaping Arrays
python
Copy
Edit
arr = np.arange(1, 31).reshape(6, 5)  # Reshape to 6 rows and 5 columns
Note: Reshaping only works if total elements remain the same.

8. Indexing and Slicing
1D Array
python
Copy
Edit
arr[6]         # Access single element
arr[3:5]       # Slice elements from index 3 to 4
2D Array
python
Copy
Edit
arr[5]         # Entire 6th row
arr[0, 0]      # Element at row 0, column 0
arr[0:2, 1:3]  # Sub-matrix slice rows 0-1, columns 1-2
arr[:, 2]      # Entire 3rd column
9. Boolean Indexing
python
Copy
Edit
arr = np.arange(11, 21)
bool_index = arr % 2 == 0
arr = arr[bool_index]     # Select only even numbers
10. Array Operations
Element-wise Operations
python
Copy
Edit
a1 + a2
a1 - a2
a1 * a2
a1 / a2
a1 // a2    # Floor division
a1 ** a2    # Exponentiation
11. Broadcasting
python
Copy
Edit
arr = np.array([10, 20, 30, 40])
arr + 10     # Add 10 to every element (broadcasting)

arr2 = np.arange(1, 26).reshape(5, 5)
arr2 = arr2 + 10    # Add 10 to each element in matrix
12. Deep and Shallow Copy
Shallow Copy (View)
python
Copy
Edit
a = np.arange(1, 21)
slice = a[:5] * 10    # Changes will NOT affect original array 'a'
13. Matrix Operations
Matrix Multiplication
python
Copy
Edit
A @ B              # Using @ operator
np.dot(A, B)       # Using np.dot()
Transpose
python
Copy
Edit
A.T
14. Stacking Arrays
python
Copy
Edit
np.vstack((a, b))           # Vertical stack
np.hstack((a, b))           # Horizontal stack
np.column_stack((a, b))     # Stack as columns
15. Splitting Arrays
python
Copy
Edit
np.hsplit(c, 4)     # Split horizontally into 4 parts
np.vsplit(c, 2)     # Split vertically into 2 parts
Note: Number of splits must exactly divide array dimension.

16. Practice: Valid Sudoku
python
Copy
Edit
# Validate that sum of rows, columns, and 3x3 blocks is 45

for i in range(0, 9, 3):
    for j in range(0, 9, 3):
        print(s[i:i+3, j:j+3].sum())    # Each block sum must be 45
17. Student Dataset Example
Dataset
python
Copy
Edit
data = np.array([
    [18, 85, 78],
    [19, 92, 88],
    [17, 76, 95],
    [18, 65, 70],
    [20, 90, 85]
])
Useful Operations:
python
Copy
Edit
data.shape                       # Shape of the dataset
np.mean(data[:, 0])              # Average age
data[:, 1]                       # All Math Marks
np.max(data[:, 2])               # Highest Science Mark
data[data[:, 1] > 90]            # Students with Math Marks > 90
data[:, 1] = data[:, 1] + 5      # Increase Math Marks by 5
len(data[data[:, 0] < 19])       # Number of students younger than 19
np.mean(data, axis=0)            # Average marks in each subject
data[(data[:, 1] > 80) & (data[:, 2] > 80)]  # Students scoring >80 in both subjects
data[data[:, 2] < 75, 2] = 0     # Replace Science Marks < 75 with 0
