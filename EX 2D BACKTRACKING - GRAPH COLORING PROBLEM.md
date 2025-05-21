# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE:
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.

## Algorithm
1. Initialize Graph: A graph is created with v vertices, represented by an adjacency matrix where graph[i][j] = 1 if an edge exists between vertex i and j.
2. Check Safety (isSafe): This function checks if a given colour c can be assigned to vertex v. It returns False if any adjacent vertex i already has the same colour c.
3. Recursive Coloring (graphColouringUtil): This is the core recursive function. It tries to color vertices one by one, starting from v=0. For each vertex, it iterates through possible m colors (1 to m).
4. Assign and Recurse: If a color c is "safe" for vertex v, it assigns c to colour[v] and recursively calls itself for the next vertex (v+1).
5. Backtrack or Succeed: If the recursive call for v+1 returns True (meaning all subsequent vertices could be colored), then the current assignment is valid, and True is returned.    

## Program:
### Developed by: NARASIMHAN S
### Register Number: 212223230133 

```
class Graph:
    def __init__(self,vertices):
        self.v=vertices
        self.graph=[[0 for column in range(vertices)] for row in range(vertices)]
    def isSafe(self,v,colour,c):
        for i in range(self.v):
            if self.graph[v][i]==1 and colour[i]==c:
                return False
        return True
    def graphColouringUtil(self,m,colour,v):
        if v==self.v:
            return True
        for c in range(1,m+1):
            if self.isSafe(v,colour,c):
                colour[v]=c
                if self.graphColouringUtil(m,colour,v+1):
                    return True
                colour[v]=0
        return False
    def graphColouring(self,m):
        colour=[0]*self.v
        if not self.graphColouringUtil(m,colour,0):
            return False
        return colour
g=Graph(4)
g.graph=[[0,1,1,1],[1,0,1,0],[1,1,0,1],[1,0,1,0]]
m=3
result=g.graphColouring(m)
if result:
    print("Solution exist and Following are the assigned colours:")
    for c in result:
        print(c,end=" ")
else:
    print("f")
```
## Output:

![image](https://github.com/user-attachments/assets/1865f4de-363c-427f-9c65-77529497598a)

## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
