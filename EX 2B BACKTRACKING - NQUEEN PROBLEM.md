# EX 2B BACKTRACKING - NQUEEN PROBLEM
## DATE:
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.

## Algorithm
1. Input N: Get the size of the chessboard (N) from the user.
2. Initialize Board: Create an N x N chessboard with all cells set to 0.
3. Place Queens (Recursive): For each column, try placing a queen in every row.
4. Check Safety: Before placing, verify the position is safe (no other queen in the same row, column, or diagonals).
5. Backtrack & Print: If a queen cannot be placed in a column, backtrack. If all N queens are placed successfully, print the board.  

## Program:
Developed by: NARASIMHAN S
Register Number: 212223230133 

```
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
            if solveNQUtil(board,col+1)==True:
                return True
            board[i][col]=0
    return False
def solveNQ():
    board = [ [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0]]
              
    if solveNQUtil(board, 0) == False:
        print ("Solution does not exist")
        return False
 
    printSolution(board)
    return True
    
solveNQ()

```
## Output:


## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.
