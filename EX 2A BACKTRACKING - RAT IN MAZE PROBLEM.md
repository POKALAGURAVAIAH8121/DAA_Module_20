# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE:
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.


## Algorithm
1. Start

2. Define the maze as a 2D list where 1 represents a valid path and 0 represents a wall.

3. Initialize a solution matrix (sol) of the same size as the maze to keep track of the path taken.

4. Implement a function (isSafe) to check if the current position is within bounds and is a valid path.

5. Use a recursive function (solveMazeUtil) to explore possible moves (down and right) from the current position. If the destination is reached, mark the path in the solution matrix.

6. If a path to the destination is found, print the solution matrix; otherwise, indicate that no solution exists.

## PROGRAM:
~~~
Program to implement Rat in a Maze.
Developed by: POKALA GURAVAIAH
Register Number: 212222040114

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
     ## Write your code here
    if x == N - 1 and y == N - 1:
        sol[x][y] = 1
        return True
    if isSafe(maze, x, y) == True:
        sol[x][y] = 1
        if solveMazeUtil(maze, x + 1, y, sol) == True:
            return True
        if solveMazeUtil(maze, x, y + 1, sol) == True:
            return True
        sol[x][y] = 0
        return False
    




# Driver program to test above function
if __name__ == "__main__":
    # Initialising the maze
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)
~~~
## Output:
<img width="500" alt="image" src="https://github.com/user-attachments/assets/9e500fc6-264d-4e57-94ca-689e3863c78e" />

## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
