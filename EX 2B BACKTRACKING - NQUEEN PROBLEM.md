# EX 2B BACKTRACKING - NQUEEN PROBLEM
## DATE:
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.


## Algorithm
1. Start from the first row and try placing a queen in each column one by one, checking for safety (no other queen in same column or diagonal).

2. If a safe position is found, place the queen and recursively try to place the next queen in the next row.

3. If placing the queen in any column doesn't lead to a solution, backtrack by removing the queen and trying the next column.

4. Repeat the process until all N queens are placed; record the solution when the base case (row == N) is reached. 

## Program:
Developed by: GANESH R

Register Number:  212222240029
```python
global N
N = int(input())
 
def printSolution(board):
    for i in range(N):
        for j in range(N):
            print(board[i][j], end = " ")
        print()
 
def isSafe(board, row, col):
 
    # Check this row on left side
    for i in range(col):
        if board[row][i] == 1:
            return False
 
    # Check upper diagonal on left side
    for i, j in zip(range(row, -1, -1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    # Check lower diagonal on left side
    for i, j in zip(range(row, N, 1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    return True
 
def solveNQUtil(board, col):
    if col>=N:
        return True
    for i in range(N):
        if isSafe(board,i,col):
            board[i][col]=1
            if solveNQUtil(board,col+1):
                return True
            board[i][col]=0
    return False
def solveNQ():
    board = [ [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0]]
 
    if solveNQUtil(board, 0) == False:
        print ("Solution does not exist")
        return False
 
    printSolution(board)
    return True
 
# Driver Code
solveNQ()


```

## Output:

![image](https://github.com/user-attachments/assets/e6c223f9-023d-487d-a309-9c74c113cf0b)


## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.
