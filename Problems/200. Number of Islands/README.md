# 200. Number of Islands

**Difficulty:** Medium  
**Topic:** DFS, Graphs, Matrix, Depth-First Search  
**Approach:** Flood Fill using DFS

## Problem Overview

Given an `m x n` grid containing `'1'` (land) and `'0'` (water), count the number of islands.

An island is formed by connecting adjacent land cells horizontally or vertically. Diagonal connections do not count.

## Approach: Depth-First Search (DFS)

The solution uses DFS to explore and mark every cell belonging to an island.

1. Traverse the entire grid.
2. Whenever a cell containing `'1'` is found, increment the island count.
3. Apply DFS from that cell to visit all its connected land cells.
4. Mark each visited land cell as `'0'` to prevent revisiting it.
5. Continue until every cell has been checked.

Each DFS traversal completely explores one island.

## Complexity Analysis

| Complexity | Value | Explanation |
|---|---|---|
| Time | `O(m × n)` | Every cell is visited at most once. |
| Space | `O(m × n)` | Recursion stack can reach this size in the worst case. |

Here, `m` represents the number of rows and `n` represents the number of columns.

## Implementations

- **C:** `solution.c`
- **Python:** `solution.py`

## Key Concepts Learned

- Depth-First Search (DFS)
- Graph traversal
- Flood Fill algorithm
- Matrix traversal
- Connected components
- In-place modification of a matrix

## Important Observation

Instead of maintaining a separate visited matrix, both implementations modify the original grid by changing visited land cells from `'1'` to `'0'`.

This avoids additional visited-array memory, although the DFS recursion stack still requires space.

---

**Core Takeaway:** An island is a connected component of land cells. DFS helps explore the entire component, allowing us to count each island exactly once.