## EX 3C Sudoku Solver
## DATE: 25/03/25

## AIM:
To write a python program to find the solution of sudoku puzzle using Backtracking.


## Algorithm
1. Traverse the board to find an empty cell (value 0).

2. Try placing digits 1–9 in that cell:

3. Check if placing the digit is valid: Not in the same row, Not in the same column and Not in the same 3×3 subgrid.

4. If valid, place the digit and recurse to solve the rest of the board.

5. If a solution is found, print the board.

6. If placing any digit fails, backtrack (reset the cell to 0).

7. Repeat until the board is filled.

## Program:
Program to implement to to find the solution of sudoku puzzle using Backtracking.

Developed by: Vidhyasri k

Register Number: 212222230170

```
board = [
    [0, 0, 0, 8, 0, 0, 4, 0, 3],
    [2, 0, 0, 0, 0, 4, 8, 9, 0],
    [0, 9, 0, 0, 0, 0, 0, 0, 2],
    [0, 0, 0, 0, 2, 9, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 7, 0, 6, 5, 0, 0, 0, 0],
    [9, 0, 0, 0, 0, 0, 0, 8, 0],
    [0, 6, 2, 7, 0, 0, 0, 0, 1],
    [4, 0, 3, 0, 0, 6, 0, 0, 0]
]

def printBoard(board):
    for i in range(0, 9):
        for j in range(0, 9):
            print(board[i][j], end=" ")
        print()

def isPossible(board, row, col, val):
    for j in range(0, 9):
        if board[row][j] == val:
            return False

    for i in range(0, 9):
        if board[i][col] == val:
            return False

    startRow = (row // 3) * 3
    startCol = (col // 3) * 3
    for i in range(0, 3):
        for j in range(0, 3):
            if board[startRow+i][startCol+j] == val:
                return False
    return True

def solve():
    for row in range(9):
        for col in range(9):
            if board[row][col] == 0:
                for val in range(1, 10):
                    if isPossible(board, row, col, val):
                        board[row][col] = val
                        solve()
                        board[row][col] = 0
                return
    printBoard(board)
    
solve()
```

## Output:
![image](https://github.com/user-attachments/assets/ca1c1e34-5fee-497b-b553-b6a892c0f816)


## Result:
The Sudoku solver program executed successfully and found the solution for the given puzzle.
