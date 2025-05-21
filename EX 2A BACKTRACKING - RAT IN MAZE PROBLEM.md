# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE:
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.


## Algorithm

1. Start at the beginning (0, 0): If the current position is the destination, add the current path to the list of solutions.

2. Mark the current cell as visited: This will help prevent revisiting the same cell.

3. Move in all four possible directions: Down, Left, Up, Right:

4. If no valid moves are possible: Backtrack by unmarking the current cell and trying a different direction.

5. Repeat the process until all possible paths are found or the destination is reached.

6. Return all paths that lead to the destination.
 

## Program:

Developed by: GANESH R

Register Number:  212222240029

```python
N = 4
 
def printSolution( sol ):
     
    for i in sol:
        for j in i:
            print(str(j) + " ", end ="")
        print("")
 

def isSafe( maze, x, y ):
     
    if x >= 0 and x < N and y >= 0 and y < N and maze[x][y] == 1:
        return True
     
    return False
 

def solveMaze( maze ):
     
    # Creating a 4 * 4 2-D list
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
     
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False
     
    printSolution(sol)
    return True
     

def solveMazeUtil(maze, x, y, sol):
    if x==N-1 and y==N-1 and maze[x][y]==1:
        sol[x][y]=1
        return True
    if isSafe(maze,x,y):
        sol[x][y]=1
        if solveMazeUtil(maze,x+1,y,sol):
            return True
        if solveMazeUtil(maze,x,y+1,sol):
            return True
        sol[x][y]=0
    return False

if __name__ == "__main__":
    # Initialising the maze
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)

```

## Output:

![image](https://github.com/user-attachments/assets/46e3ae11-167c-4aa2-924a-bc3adc993160)


## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
