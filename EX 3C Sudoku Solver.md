# EX 3C Sudoku Solver
## DATE: 27.04.2025
## AIM:
To write a python program to find the solution of sudoku puzzle using Backtracking.

## Algorithm
1. Start the program.
2. Define the function "isPossible(board, row, col, val)".
3. Check if val is already present in the given row.
   Check if val is already present in the given column.
   Check if val is already present in the 3x3 sub-grid to which (row, col) belongs.
4. Return True if placing val at (row, col) is valid. False otherwise.
5. Define the function "solve()"
   Loop through each cell (i, j) in the board.
   If the cell is empty (board[i][j] == 0): Try all numbers 1 through 9:
        If isPossible(board, i, j, num) returns True:
        Place num in the cell: board[i][j] = num.
        Recursively call solve() to solve the rest of the board.
        If a solution is not found, reset the cell: board[i][j] = 0 (backtrack).
   Return immediately after attempting to fill the cell, since we need to try all possibilities at that position before moving forward.
7. If the loop completes (i.e., no empty cells remain), the board is solved.
8. Call printBoard(board) to display the solution.
9. End the program.
   

## Program:
```
Program to implement to to find the solution of sudoku puzzle using Backtracking.
Developed by: SATHYAA R
Register Number: 212223100052
```

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
    for i in range(9):
        for j in range(9):
            if board[i][j] == 0:
                for num in range(1, 10):
                    if isPossible(board, i, j, num):
                        board[i][j] = num
                        solve()  
                        board[i][j] = 0  
                return
    printBoard(board)
    
solve()
```


## Output:

![image](https://github.com/user-attachments/assets/e6e0d1aa-2f2d-41c1-bd7e-7ef4bc682109)


## Result:
The Sudoku solver program executed successfully and found the solution for the given puzzle.
