## EX 3A Knight Tour & Count Path
## DATE: 18/03/25

## AIM:
To write a python program to find minimum steps to reach to specific cell in minimum moves by knight

## Algorithm
1. Initialize all 8 possible knight moves.

2. Create a queue and enqueue the knight's starting position with distance 0.

3. Mark the starting cell as visited.

4. While the queue is not empty:

5. Dequeue a cell.

6. If it's the target position, return the distance.

7. For each of 8 moves:

8. Compute new position.

9. If it's inside the board and not visited:

10. Mark as visited and enqueue with distance +1.

11. If target not reached, return infinity (unreachable).

## Program:
Program to implement to find minimum steps to reach to specific cell in minimum moves by knight.

Developed by: Vidhyasri k
Register Number: 212222230170

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
![image](https://github.com/user-attachments/assets/dfcbf5a8-404e-4820-94f3-f792e1ddf87e)


## Result:
The program executed successfully, and the minimum number of steps for the knight to reach the target was calculated.
