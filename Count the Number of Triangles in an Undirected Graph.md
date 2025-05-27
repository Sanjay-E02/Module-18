# Ex. No: 18E - Count the Number of Triangles in an Undirected Graph

## AIM:
To write a Python program to **count the number of triangles** present in an **undirected graph** using matrix operations.

## ALGORITHM:

**Step 1**: Initialize a matrix `aux2` to store the square of the adjacency matrix (i.e., `graph²`).  
Also, initialize a matrix `aux3` to store the cube of the adjacency matrix (i.e., `graph³`).

**Step 2**: Multiply the adjacency matrix with itself to compute `aux2 = graph × graph`.

**Step 3**: Multiply `aux2` with the adjacency matrix again to compute `aux3 = aux2 × graph`.

**Step 4**: Compute the **trace** of the matrix `aux3` (i.e., the sum of diagonal elements of the matrix).

**Step 5**: Divide the trace by **6** to get the number of triangles in the graph.  
*(Each triangle is counted six times in the trace — twice per vertex and once per direction.)*

**Step 6**: Return the result.

## PYTHON PROGRAM
```
import numpy as np

def count_triangles(adj_matrix):
    # Step 1: Convert to numpy array for matrix operations
    A = np.array(adj_matrix)

    # Step 2: Compute A^3
    A2 = np.matmul(A, A)
    A3 = np.matmul(A2, A)

    # Step 3: Trace of A^3
    trace = np.trace(A3)

    # Step 4: Each triangle is counted 6 times
    return trace // 6

# Example: Undirected graph with 4 vertices and 2 triangles
adj_matrix = [
    [0, 1, 1, 0],
    [1, 0, 1, 1],
    [1, 1, 0, 1],
    [0, 1, 1, 0]
]

print("Number of triangles:", count_triangles(adj_matrix))
````
## OUTPUT:
![image](https://github.com/user-attachments/assets/3efc08b8-80fd-4503-9554-665a1c46fb89)


## RESULT
Thus,a Python program to count the number of triangles present in an undirected graph using matrix operations was successfully implemented and verified.
