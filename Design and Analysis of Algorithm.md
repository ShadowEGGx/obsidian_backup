### What is Algorithm?
**Algorithm** can be defined as a set of instructions on basis of which a program can work.

#### Efficiency of an Algorithm
Algorithm's efficiency (time taken by the algorithm to execute the program) can be represented by **asymptotic** notations. 
Asymptotic notations: Manual mathematical calculations (called **apriori analysis**) that are done during the dry run of the program before compilation. It means a line where distance to a given curve tends to zero.
##### Complexity:
- **Time Complexity:** Time taken by the program to execute. Represented by $f(n)$. $n$ is the input to define the number of iterations.
- **Space Complexity:** Space in bytes taken by the program.

If not specified otherwise, complexity means the time complexity.

##### Asymptotic Notations:
- **Big O notation**: Measures the upper bound of execution graph. Measures *maximum time* taken by the program to execute. $f(n)$ is maximum.
- **Omega notation (Ω)**: Measures the lower bound of execution graph. Measures *minimum time* taken by the program to execute. $f(n)$ is minimum.
- **Theta notation (ϴ)**: Combination of Big O and Omega notations to define the *actual time* taken by the program to execute. It represents the *tight bound*, i.e. the the range between upper bound and lower bound. $f(n)$ is average.

###### Questions:
1. Consider the following pseudo codes. Determine f(n).
```C
Algorithm sum(Add) {
	s = 0; // (1)
	for (i = 0; i < n; i++) // (n+1)
		s = s + A[i]; // (n)
	return s; // (1)
}
```
Here: $f(n) = 1 + (n+1) + n + 1 = 2n + 3$

```C
Algorithm add(A, B, n) {
	for (i = 0; i < n; i++) { // (n+1)
		for (j = 0; j < n; j++) { // (n(n+1))
			C[i, j] = A[i, j] + B[i, j]; // (n^2)
			}
		}	
}
```
Here: $f(n) = (n+1) + n(n+1) + (n^2)$
		= $2n^2 + 2n + 1$

```C
Algorithm Multiply(A, B, n) {
	for (i = 0; i < n; i++) { // (n+1)
		for (j = 0; j < n; j++) { // (n(n+1))
			c[i, j] = 0; // (n^2)
			for (k = 0; k < n; k++) { // (n^2(n+1))
				c[i, j] = c[i,j] + A[i, j] * B[k, j]; // (n^3)
				}
			}
		}
}
```
Here: $f(n) = (n+1)+(n(n+1))+(n^2)+(n^2(n+1)+(n^3)$
		= $2n^3+3n^2+2n+1$

```C
for (i = n; i > 0; i--) { // (n+1)
	printf("%d", i); // (n)
}
```
Here

```C
for (i = 1; i < n; i = i + 2) { // (n-1)
	printf("%d", i); // ⌊n/2⌋
}
```
Here: $f(n)=(n-1) + n/2$
		= $2n-1$

[In this subject, write Algorithms, Pseudocode and main code in lab]

#### Types of Algorithms
1. **Sorting Algorithm**
	- Used to arrange data in a particular order.
	- *For example:* Bubble Sort, Quick Sort, Insertion Sort, etc.
2. **Searching Algorithm**
	- Used to find specific elements within a data structure.
	- *Example*: Linear search, Binary search
3. **Divide and Conquer Algorithm**
	- Break down a problem into smaller sub problems, solve each one individually and combine the results.
	- *Example*: Merge Sort, Quick Sort, etc.
4. **Dynamic Program Algorithm**
	- Solved complex problems by breaking them into simple sub problems, solving each sub problem once, and storing the results for future use.
	- *Example:* Fibonacci Sequence, Knapsack problem
5. **Greedy Algorithm**
	- Make the best choice at each step with the hope of finding the global optimum.
	- *Example*: Dijkstra's Algorithm, Prims Algorithm, etc.
6. **Backtracking Algorithm**
	- Solve problems incrementally by trying partial solutions and then abandoning them if they are not viable.
	- *Example:* Sudoku Solver, N-Queen's Problem, etc.
7. **Graph Algorithm**
	- Used to solve problems related to graphs such as finding the shortest path or detecting cycles.
	- *Example:* Dijkstra's Algorithm, Bellman-Ford Algorithm
8. **Recursive Algorithm**
	- Solved problems by calling themselves with modified parameters
	- *Example:* Factorial Calculations, Tower of Hanoi
9. **Brute Force Algorithm**
	- Try all possible solutions for the best one.
	- *Example:* Travelling salesman problem

###### Questions
1. Solve for f(n)
```c
for (i = 0; i < 1; i++) { // n+1
	for (j = 0; j < 1; j++) { // n(n+1)
		smt;
	}
	int p = 0 // n
}
```
Here: $f(n) = (n+1)+(n(n+1))+n =$ 

```C
for (i = 1; p < n; i++) {
	p = p + i;
}
```
Here: $f(n) =$ 

```C
for (i = 1; i < n; i+2) { 
	smt;
}
```


2. How many times will `smt` be executed, when $n = k$
```c
for (i = 0; i < 1; i++) { // n+1
	for (j = 0; j < 1; j++) { // n(n+1)
		smt;
	}
```

| `i` | `j`     | `smt` |
| --- | ------- | ----- |
| 0   | 0       | 0     |
| 1   | 0, 1    | 1     |
| 2   | 0, 1, 2 | 2     |
| ... |         |       |
| k   | k + 1   | k     |


#### Find time complexity
#### Recurrence Relations
Find the time complexity of the following recurrence relation:
T(n) = 2T(n/2) + n for n > 1
	= 1                  for n = 1

