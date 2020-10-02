---
title: Matrix Diagonal Sum
category:
link: https://leetcode.com/problems/matrix-diagonal-sum/
gh_comments_issue_id:
tags:
  - unsolved
---

## Problem

Given a square matrix `mat`, return the sum of the matrix diagonals.

```python
# Example Input
mat = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
]

# Example Output
25

# Explanation (note that 5 is not repeated)
1 + 5 + 9 + 3 + 7 == 25
```

## Solution

```python
def diagonal_sum(mat):
  sum = 0
  middle = len(mat) // 2
  hasmiddle = True if len(mat) % 2 != 0 else False

  for row in range(len(mat)):
    # In left diag, row = column indices in NxN matrix
    sum += mat[row][row]
    #right diag, column indices are different
    col = len(mat) - 1 - row
    if not hasmiddle or (hasmiddle and (row != middle) and (col != middle)):
      sum += mat[row][col]


  return sum
# Tests
assert diagonal_sum([[1,2,3],[4,5,6],[7,8,9]]) == 25
```
