## Arrays
### What is an Array?
An **Array** is a data structure that stores multiple elements of a homogeneous datatype under a single variable name. Each element in an array has an *index* or a key.

In C language, an array can be defined by: `int arr[5] = {1, 2, 3, 4, 5};`
Here `arr[5]` means the array stores 5 integer elements.

### Array Basics
- #### Advantages of using Array
  -> Easy to access elements using indices.
  -> Useful for representing large amounts of data.
- #### Limitations of Array
  -> Fixed size (cannot resize after redeclaration).
  -> Contagious memory requirement. (i.e. stores data in the computer's memory in a sequential and uninterrupted manner.)

### Array Initialization
An array can be initialized in the following ways:

- #### Static Initialization
```C
int arr[5] = {1, 2, 3, 4, 5};  // initialized with values
int arr[5] = {0};              // all values initialized with 0
int arr[5];                    // uninitialized array; may contain garbage values
```

- #### Dynamic Initialization (Assigning values at runtime)
```C
int arr[6];
for (int i = 0; i < 6; i++) {
	arr[i] = i * 2;             // example: fill with even numbers
}
```

### Accessing Array Elements
- Using **Index: `arr[i]`**
- Example: Print all elements in the Array
```C
for (int i = 0; i < 6; i++) {
	printf("%d", arr[i]);
}
```

### Array size calculation
- Use the **`sizeof`** operator:
```C
int arr[5];
int size = sizeof(arr) / sizeof(arr[0]);  // gives the total number of elements
```

### Multidimensional Arrays
- Multidimesional Arrays could be thought of matrices. There can be 2D or 3D arrays.
- Initialization and Declaration:
```C
int arr[3][3] = {
	{1, 2, 3}
	{4, 5, 6}
	{7, 8, 9}
};
```
- Accessing array elements using `arr[i][j]`.

### Using Pointers with Arrays
- **Pointer:** A variable with a certain datatype that points to the memory address/location of another variable.
- In C, the name of the array acts as a pointer to the first element of the array.
```C
int arr[6] = {2, 4, 6, 8, 10, 12};
printf("%p", arr);        // address of the first element
printf("%p", &arr[0]);    // same address as arr
```

### Accessing Array elements using Pointers
- Using pointer arithmetic:
```C
int arr[5] = {1, 2, 3, 4, 5};
int *ptr = arr;                   // pointer to the first element
for (int i = 0; i < 5; i++) {
	printf("%d ", *(ptr + i));    // accessing elements using pointer
}
```

### Pointer to an Array
- Declaration and usage:
```C
int arr[5] = {1, 2, 3, 4, 5};
int (*ptr)[5] = &arr;             // pointer to the entire array
printf("%d \n", (*ptr)[2])        // access the 3rd element
```

### Passing Arrays to Functions
- Arrays are passed to functions as pointers and not by value. (Call by Reference is used)
- Usage:
```C
void printArr(int *arr, int size) {
	for (int i = 0; i < size; i++) {
		printf("%d ", arr[i]);
	}
}
int main() {
	int arr[5] = {1, 2, 3, 4, 5};
	printArr(arr, 5);             // passed the array to the function
	return 0;
}
```

### Pointer notation v/s Array indexing
- Pointer notation can replace array indexing:
```C
arr[i] = *(arr + i);     // both are equivalent
```

## Dynamic Memory Allocation

### What is Dynamic Memory Allocation?
It is a memory allocation that allows program to request memory at runtime, which is particularly useful when the size of contagious data structures (like arrays) cannot be determined at compile time.

### Why use Dynamic Memory Allocation?
- **Flexibility**: Allocate memory as needed during program execution.
- **Efficient Memory Usage**: Allocate only the required memory, reducing wastage.
- **Dynamic Data Structures**: Create structures like linked lists, trees, and graphs that grow and shrink at runtime.

### Memory Allocation Functions in C
#### `malloc()` (Memory Allocation)
- Allocates a block of memory of a specified size in bytes.
- Returns a pointer to the first byte of the allocated memory.
- The memory is uninitialized.
- Syntax:
```C
void* malloc(size_t size);
```

Example:
```C
int *arr = (int *)malloc(5 * sizeof(int));  // Allocates memory for 5 integers
if (arr == NULL) {
    printf("Memory allocation failed\n");
}
```

#### `calloc()` (Contagious Allocation)
- Changes the size of previously allocated memory.
- Useful for resizing arrays dynamically.
- Syntax:
```C
void* calloc(size_t num, size_t size);
```

Example:
```C
int *arr = (int *)calloc(5, sizeof(int));  // Allocates memory for 5 integers
                                           // and initialize them to 0
```

#### `realloc()` (Reallocate Memory)
- Changes the size of previously allocated memory.
- Useful for resizing arrays dynamically.
- Syntax:
```C
void* realloc(void* ptr, size_t newSize);
```

Example:
```C
arr = (int *)realloc(arr, 10 * sizeof(int));
if (arr == NULL) {
	printf("Memory Allocation Failed.");
}
```

#### `free()` (Deallocate Memory)
- Frees previously allocated memory.
- Syntax:
```C
void free(void* ptr);
```

Example:
```C
free(arr); // releases memory back to the system
```


## Introduction to Data Structure
### 1. What is a Data Structure? List the various linear and non-linear data structures and explain them in brief.

A data structure is a way of organising, managing and storing data in a computer that it can be accessed and modified efficiently. It defines the relationship between the data, operations that can be performed on the data, and the logic to manipulate it. As water is to a container, data are to be a data structure.

Data structure can be divided into **Linear DS** and **Non-Linear DS**.
- *Linear Data Structures*
	1. Sequential: Array, Stack, Queue, Priority Queue
	2. Linked: Linked List, Linked Stack, Linked Queue.
- *Non-Linear Data Structures*
	1. Tree
	2. Graphs

### 2. What is Abstract Data Type?

An **Abstract Data Type (ADT)** is a theoretical concept in computer science that defines a data type purely by its **behavior (operations)** rather than its implementation. It specifies _what_ operations can be performed on the data and _how_ the data behaves, but not _how_ these operations are implemented.

### 3. Write the Applications of Data Structures.

Data Structures are used in:
- Database Management Systems (DBMS) 
- Computer Networking
- Compiler Designs
- Automated Theory
- AI
- Neural Network
- Deep Neural Network
- Computer Graphics
- Animation
- Image Processing.

### 4. Operations on a Data Structure.

The following operations can be performed on a DS:
1. Searching
2. Sorting
3. Insertion
4. Deletion
5. Merging
6. Traversing

### 5. Differentiate Between:
#### a) Linear and Non-Linear DS

| **Aspect**           | **Linear DS**                                                                                    | **Non-Linear DS**                                                                  |
| -------------------- | ------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------- |
| *Defintion*          | Data is organised in a sequential order, forming a straight line.                                | Data is organised hierarchically or in a non-sequential order.                     |
| *Connectivity*       | Every element is connected to its previous and next element (expect the first and last elements) | Each element (node) may be connected to multiple elements in different ways.       |
| *Traversal*          | Traversed in a single run (linear order).                                                        | Traversal can be hierarchical (e.g. depth-first, breadth-first).                   |
| *Memory Utilization* | Memory utilization is generally sequential and contiguous (except linked lists)                  | Memory is allocated dynamically and relationships are established using pointers.  |
| *Usage*              | Used for tasks like temporary storage, sequential processing and simple data operations.         | Used for hierarchical relationships, network modelling and dynamic decision-making |
| *Examples*           | Array, Linked Lists, Stacks, Queue                                                               | Tree, Graph                                                                        |
#### b) Primitive and Non-Primitive Data Structures
| **Aspect**            | **Primitive DS**                                                   | **Non-Primitive DS**                                                       |
| --------------------- | ------------------------------------------------------------------ | -------------------------------------------------------------------------- |
| *Definition*          | Basic, predefined data types provided by the programming language. | Complex data types derived from primitive data structures.                 |
| *Data Representation* | Represents single values or basic types of information.            | Represents collections of data or relationships between data.              |
| *Data Manipulation*   | Direct manipulation of values.                                     | Requires methods or algorithms to manage data (e.g. traversal, insertion). |
| *Dependency*          | Independent and self-contained.                                    | Depends on primitive data types for implementation.                        |
| *Examples*            | `int`, `char`, `float`, `bool`                                     | Arrays, linked lists, stacks, queues, tress, graphs.                       |

