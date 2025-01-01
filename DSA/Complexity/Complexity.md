# Understanding Big-O, Big-Theta, and Big-Omega Notations

These notations are used to describe the time complexity (how time grows with input size) and space complexity (how memory grows with input size) of an algorithm.

## 1. Big-O Notation

- Describes the upper bound of an algorithm's growth rate.
- Represents the worst-case scenario.
- Ensures that the algorithm will not take more time than a certain value as the input size grows.

### Example
If an algorithm takes f(n) = 2n + 3 operations for an input of size n, we simplify this to O(n) because:

- At large n, the constant (3) and coefficient (2) become negligible compared to the dominant term n.

### Real-World Analogy
If a train runs at a max speed of 100 km/h, you know it won’t exceed this speed regardless of the situation.

## 2. Big-Theta Notation

- Describes the tight bound (exact growth rate) of an algorithm.
- Represents both the best-case and worst-case scenarios.
- Ensures that the algorithm's time complexity is always proportional to a specific rate.

### Example
For the same f(n) = 2n + 3, we say it is Θ(n) because:

- The algorithm’s performance grows exactly proportional to n for large inputs.

### Real-World Analogy
If a train always runs at 60 km/h, no matter the weather or traffic, this is its tight bound.

## 3. Big-Omega Notation

- Describes the lower bound of an algorithm's growth rate.
- Represents the best-case scenario.
- Guarantees that the algorithm will take at least this much time.

### Example
If an algorithm takes f(n) = 2n + 3, its best-case time complexity is also Ω(n) because:

- It cannot take less than n time for large inputs.

### Real-World Analogy
A train’s minimum speed on a clear track might always be 40 km/h.

## Key Relationship Between Big-O, Big-Theta, and Big-Omega

- Big-O: How fast an algorithm could grow.
- Big-Theta: How fast it does grow.
- Big-Omega: How slow it could grow.

## Analyzing Complexity of Basic Loops

### Case 1: Single Loop
```python
for i in range(n):  # n iterations
    print(i)  # O(1) operation
```
**Analysis:**
- The loop runs n times.
- Each iteration performs an O(1) operation.
- **Time Complexity:** O(n)

### Case 2: Nested Loop
```python
for i in range(n):  # Outer loop runs n times
    for j in range(n):  # Inner loop runs n times for each outer loop
        print(i, j)  # O(1) operation
```
**Analysis:**
- The outer loop runs n times.
- For each iteration of the outer loop, the inner loop also runs n times.
- Total iterations: n \* n = n².
- **Time Complexity:** O(n²)

### Case 3: Loop with Logarithmic Growth
```python
i = 1
while i < n:  # Logarithmic growth
    print(i)  # O(1) operation
    i *= 2  # `i` doubles each time
```
**Analysis:**
- i takes the values 1, 2, 4, 8, ..., n.
- The number of iterations is proportional to log₂(n).
- **Time Complexity:** O(log n)

### Case 4: Loop with Variable Increment
```python
for i in range(1, n, 2):  # Increment by 2
    print(i)  # O(1) operation
```
**Analysis:**
- The loop runs for half of n iterations.
- **Time Complexity:** O(n/2) simplifies to O(n) (drop constants).

## Practical Examples

### Example 1: Analyzing Single Loop
```python
for i in range(1000):  # Loop runs exactly 1000 times
    print(i)  # O(1)
```
**Time Complexity:** O(1) because the number of iterations is constant, independent of n.

### Example 2: Analyzing Nested Loops
```python
for i in range(n):  # Outer loop
    for j in range(n):  # Inner loop
        print(i, j)  # O(1)
```
**Time Complexity:** O(n²) because the total iterations are n \* n.

### Example 3: Combining Loops
```python
for i in range(n):  # O(n)
    print(i)

for j in range(n):  # O(n)
    print(j)
```
**Time Complexity:** O(n) + O(n) = O(2n) simplifies to O(n).

