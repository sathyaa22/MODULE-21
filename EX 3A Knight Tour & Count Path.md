# EX 3A Knight Tour & Count Path
## DATE: 24.04.025
## AIM:
To write a python program to find minimum steps to reach to specific cell in minimum moves by knight


## Algorithm
1. Start the program.
2. Input:
   Size of the board N
   Starting position of the knight knightpos = [x1, y1]
   Target position targetpos = [x2, y2]
3. Create a class cell with:
   x, y: current coordinates
   dist: number of steps taken to reach this cell
4. Define isInside(x, y, N)
5. Return True if the cell (x, y) lies within the board limits 1 ≤ x, y ≤ N, else False.
6. Define arrays for the 8 possible moves of a knight:
7. Initialize a queue for BFS and add the starting position as the first cell with dist = 0.
8. Initialize a 2D array visited[N+1][N+1] to track visited positions.
9. While the queue is not empty:
   Remove the front cell from the queue → curr
   If curr.x == target.x and curr.y == target.y, return curr.dist as the result.
   Else:
   For each of the 8 knight moves: Calculate the next position (x, y). If isInside(x, y, N) and not visited[x][y]: Mark as visited and enqueue cell(x, y, curr.dist + 1)
10. If no path found, return infinity (or a message indicating unreachable)
11. End the program.
     

## Program:
```
Program to implement to find minimum steps to reach to specific cell in minimum moves by knight.
Developed by: SATHYAA R
Register Number: 212223100052
```

```
class cell:
    def __init__(self, x = 0, y = 0, dist = 0):
        self.x = x
        self.y = y
        self.dist = dist

def isInside(x, y, N):
    if (x >= 1 and x <= N and
        y >= 1 and y <= N):
        return True
    return False

def minStepToReachTarget(knightpos,
                         targetpos, N):
    dx = [-2, -1, 1, 2, -2, -1, 1, 2]
    dy = [-1, -2, -2, -1, 1, 2, 2, 1]

    queue = []
    queue.append(cell(knightpos[0], knightpos[1], 0))
    visited = [[False for _ in range(N + 1)] for _ in range(N + 1)]
    visited[knightpos[0]][knightpos[1]] = True

    while len(queue) > 0:
        curr = queue.pop(0)
        if curr.x == targetpos[0] and curr.y == targetpos[1]:
            return curr.dist
        for i in range(8):
            x = curr.x + dx[i]
            y = curr.y + dy[i]
            if isInside(x, y, N) and not visited[x][y]:
                visited[x][y] = True
                queue.append(cell(x, y, curr.dist + 1))
    return float('inf')
    
if __name__=='__main__':
    N = 30
    knightpos = [1, 1]
    targetpos = [30, 30]
    print(minStepToReachTarget(knightpos,
                               targetpos, N))
```


## Output:

![image](https://github.com/user-attachments/assets/744e7537-3882-4ec7-b44c-55442c49f83f)


## Result:
The program executed successfully, and the minimum number of steps for the knight to reach the target was calculated.
