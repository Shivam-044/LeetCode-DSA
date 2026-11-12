# 0912. Sort an Array

**Platform:** LeetCode  
**Difficulty:** Medium  
**Topics:** Array, Divide and Conquer, Sorting, Recursion, Merge Sort

[🔗 View Problem on LeetCode](https://leetcode.com/problems/sort-an-array/)

## Problem Overview

Given an integer array `nums`, sort its elements in ascending order and return the sorted array.

The objective is to implement an efficient sorting algorithm rather than relying on built-in sorting functions.

**Example:**

- Input: `nums = [5, 2, 3, 1]`
- Output: `[1, 2, 3, 5]`

## Approach: Merge Sort (Divide and Conquer)

Use the Merge Sort algorithm, which follows the Divide and Conquer paradigm.

The algorithm recursively divides the array into smaller subarrays, sorts them independently, and merges them to produce the final sorted array.

### Algorithm

1. **Divide:** Find the middle index and split the array into two halves.
2. **Conquer:** Recursively apply Merge Sort to both halves until each subarray contains at most one element.
3. **Merge:** Compare elements from both sorted halves and place the smaller element into the resulting sorted sequence.
4. **Combine:** Append any remaining elements and continue merging until the complete array is sorted.

### Visual Representation

For example, consider:

```text
Original Array:
[5, 2, 3, 1]

       Divide
      /      \
   [5, 2]   [3, 1]
    /  \     /  \
  [5]  [2] [3]  [1]

       Merge
      /      \
   [2, 5]   [1, 3]

         |
       Final
    [1, 2, 3, 5]
```

## Implementation Details

### C Implementation

- Uses recursive `mergeSort()` to divide the array.
- The `merge()` function creates temporary left and right arrays.
- Sorted elements are merged back into the original array.
- Allocated temporary memory is released using `free()`.

### Python Implementation

- Uses recursive slicing to divide the array into smaller halves.
- Recursively sorts both halves.
- The `merge()` function creates a new sorted list by comparing elements.
- Remaining elements are appended using `extend()`.

Both implementations use the same Merge Sort algorithm but differ in how they manage memory and construct the sorted result.

## Complexity Analysis

Let `n` represent the number of elements in the input array.

| Complexity | Value | Explanation |
|---|---|---|
| Time | O(n log n) | The array is divided into logarithmic levels, with O(n) work at each level. |
| Auxiliary Space | O(n) | Temporary arrays or lists are required during merging. |
| Recursion Stack | O(log n) | Recursive calls follow the depth of the division tree. |

### Algorithm Properties

- **Sorting Technique:** Divide and Conquer
- **Sorting Order:** Ascending
- **Stability:** Stable
- **Approach:** Top-Down Recursive Merge Sort

The implementations use `<=` when comparing elements, ensuring that equal elements from the left half retain their relative order during merging.

## Implementations

| Language | Algorithm | File |
|---|---|---|
| C | Recursive Merge Sort | [solution.c](./solution.c) |
| Python | Recursive Merge Sort | [solution.py](./solution.py) |

---

*Key takeaway: Merge Sort demonstrates how a complex problem can be broken into smaller, manageable subproblems. By combining their solutions efficiently, it achieves O(n log n) time complexity.*