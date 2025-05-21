# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE:
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.



## Algorithm
1. Recursive Exploration: The algorithm tries to assign colors to vertices one by one, exploring all possible colorings using recursion.

2. Safety Check: Before assigning a color to a vertex, it checks if the same color is already used by any adjacent vertex to maintain validity.

3. Backtracking: If a color assignment leads to a conflict later, the algorithm backtracks by unassigning the color and trying the next available one.

4. Color Minimization: The goal is to find a valid coloring using at most M colors, ideally minimizing M to achieve the most efficient coloring.

## Program:

Developed by: GANESH R

Register Number:  212222240029
```python
class Graph:
 
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [[0 for _ in range(vertices)] for _ in range(vertices)]
 
    def isSafe(self, v, colour, c):
        for i in range(self.V):
            if self.graph[v][i] == 1 and colour[i] == c:
                return False
        return True
 
    def graphColourUtil(self, m, colour, v):
        if v == self.V:
            return True

        for c in range(1, m + 1):
            if self.isSafe(v, colour, c):
                colour[v] = c
                if self.graphColourUtil(m, colour, v + 1):
                    return True
                colour[v] = 0  # Backtrack if assigning color c doesn't lead to a solution

    def graphColouring(self, m):
        colour = [0] * self.V
        if not self.graphColourUtil(m, colour, 0):
            print("Solution does not exist")
            return False

        print("Solution exist and Following are the assigned colours:")
        for c in colour:
            print(c, end=' ')
        return True


```

## Output:
![image](https://github.com/user-attachments/assets/86c5b4f9-ebd0-4d90-b4a2-ad4ff8ca917b)



## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
