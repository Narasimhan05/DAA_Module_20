# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE:
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.


## Algorithm
1. Initialize: Create a 4x4 maze and an empty 4x4 solution matrix.
2. Start Solving (Recursive): Begin at (0,0) and mark the current cell in the solution.
3. Explore Paths: Recursively try moving down (x+1, y) then right (x, y+1), checking if the move is safe (within bounds and a '1' in the maze).
4. Backtrack if Blocked: If a path leads to a dead end or no solution is found from that point, unmark the current cell (backtrack).
5. Print Solution: If the destination (3,3) is reached, print the solution matrix; otherwise, report that no solution exists.   

## Program:
### Developed by: NARASIMHAN S
### Register Number: 212223230133 

```
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
    if x==N-1 and y==N-1:
        sol[x][y]=1
        return True
    if isSafe(maze,x,y)==True:
        sol[x][y]=1
        if solveMazeUtil(maze,x+1,y,sol)==True:
            return True
        if solveMazeUtil(maze,x,y+1,sol)==True:
            return True
        sol[x][y]=0
        return False
    return False

# Driver program to test above function
if __name__ == "__main__":
    # Initialising the maze
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)
```

## Output:

![image](https://github.com/user-attachments/assets/070e8a6a-ac6d-4f1b-bd06-91bdc0761f52)

## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
