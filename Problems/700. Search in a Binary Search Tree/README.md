# 0700. Search in a Binary Search Tree

**Platform:** LeetCode  
**Difficulty:** Easy  
**Topics:** Binary Search Tree, Binary Tree, Tree Traversal

[🔗 View Problem on LeetCode](https://leetcode.com/problems/search-in-a-binary-search-tree/)

## Problem Overview

Given the root of a Binary Search Tree (BST) and an integer `val`, find the node whose value matches `val`.

Return the subtree rooted at the matching node. If the value does not exist, return `null`.

## Approach: Iterative BST Traversal

Use the Binary Search Tree property to navigate directly towards the target instead of traversing every node.

### BST Property

For every node in a Binary Search Tree:

- Values in the left subtree are smaller than the current node.
- Values in the right subtree are greater than the current node.

### Algorithm

1. Start searching from the root node.
2. Continue while the current node exists and its value does not match the target.
3. Compare the target value with the current node:
   - If `val` is smaller, move to the left child.
   - If `val` is greater, move to the right child.
4. If a matching node is found, return it.
5. If the traversal reaches `null`, the target does not exist in the tree, so return `null`.

This approach eliminates unnecessary traversal by using the ordering property of the BST.

## Complexity Analysis

Let `h` represent the height of the Binary Search Tree.

| Complexity | Value | Explanation |
|---|---|---|
| Time | O(h) | Each step moves to one child, visiting at most one node per tree level. |
| Auxiliary Space | O(1) | Iterative traversal uses only a constant amount of extra memory. |

**Depending on tree structure:**

- Balanced BST: O(log n) time.
- Skewed BST: O(n) time.

## Implementations

| Language | Approach | File |
|---|---|---|
| C | Iterative BST Traversal | [Solution.c](./Solution.c) |
| Java | Iterative BST Traversal | [Solution.java](./Solution.java) |
| Python | Iterative BST Traversal | [Solution.py](./Solution.py) |

All three implementations follow the same iterative search strategy and return the matching subtree or `null` if the target is absent.

## Key Takeaway

A Binary Search Tree is more than a binary tree. Its ordering property allows us to eliminate half of the possible search directions at every step, avoiding unnecessary node visits.

*Good algorithms don't just process data efficiently; they use the structure of the data to avoid unnecessary work.*