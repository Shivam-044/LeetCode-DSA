# 0215. Kth Largest Element in an Array

**Platform:** LeetCode  
**Difficulty:** Medium  
**Topics:** Array, Sorting, Heap, Priority Queue, Divide and Conquer

[🔗 View Problem on LeetCode](https://leetcode.com/problems/kth-largest-element-in-an-array/)

## Problem Overview

Given an integer array `nums` and an integer `k`, find the kth largest element in the array.

The kth largest element is determined by its position in sorted order, not by its distinct value. Duplicate elements are counted separately.

**Example:**

- Input: `nums = [3, 2, 1, 5, 6, 4]`, `k = 2`
- Output: `5`
- Explanation: The sorted array is `[1, 2, 3, 4, 5, 6]`. The second largest element is `5`.

## Approach 1: Min Heap (Top-K Elements) — C

Maintain a Min Heap containing only the largest `k` elements encountered so far.

The smallest element in this heap represents the kth largest element in the original array.

### Algorithm

1. Allocate memory for a heap of size `k`.
2. Insert the first `k` elements of the array into the heap.
3. Build a Min Heap using `minHeapify()`.
4. Traverse the remaining elements:
   - Compare the current element with the root of the heap.
   - If it is greater, replace the root with the current element.
   - Restore the Min Heap property using `minHeapify()`.
5. After processing all elements, the root contains the kth largest element.
6. Store the result, release the allocated memory, and return the answer.

### Key Concepts

- **Min Heap:** A complete binary tree in which every parent is smaller than or equal to its children.
- **Heapify:** Restores the Min Heap property after replacing an element.
- **Top-K Selection:** Maintains only the k largest elements instead of sorting the entire array.

## Approach 2: Sorting — Java

Sort the entire array in ascending order and directly access the kth largest element using its index.

### Algorithm

1. Sort the array using `Arrays.sort(nums)`.
2. The largest element is at index `nums.length - 1`.
3. Therefore, the kth largest element is at index `nums.length - k`.
4. Return `nums[nums.length - k]`.

This approach uses the sorted order of the array to locate the required element directly.

## Approach Comparison

| Feature | C: Min Heap | Java: Sorting |
|---|---|---|
| Strategy | Top-K selection | Full sorting |
| Main concept | Heap | Sorting |
| Time complexity | O(n log k) | O(n log n) typically |
| Auxiliary space | O(k) | Depends on sorting implementation |
| Input modification | No | Yes |
| Best suited for | Small k relative to n | Simple implementation |

## Complexity Analysis

Let `n` represent the number of elements in the array and `k` the required position.

### C — Min Heap

| Operation | Complexity |
|---|---|
| Initial heap creation | O(k) |
| Heap construction | O(k) |
| Processing remaining elements | O((n-k) log k) |
| Retrieving the answer | O(1) |
| Auxiliary space | O(k) |

**Overall Time:** O(n log k)

**Auxiliary Space:** O(k), excluding the recursive heapify call stack.

### Java — Sorting

| Operation | Complexity |
|---|---|
| Array sorting | O(n log n) typically |
| Accessing kth largest element | O(1) |
| Auxiliary space | Depends on sorting implementation |

**Overall Time:** O(n log n) typically.

## Implementations

| Language | Algorithm | File |
|---|---|---|
| C | Min Heap (Top-K Elements) | [Solution.c](./Solution.c) |
| Java | Array Sorting | [Solution.java](./Solution.java) |

---

## Interview Insight

The Min Heap approach is particularly useful when `k` is much smaller than `n`.

Instead of sorting all `n` elements, it maintains only `k` candidates, reducing the time complexity to O(n log k).

For example, if an array contains 100,000 elements and we need only the 3rd largest element, maintaining a heap of size 3 avoids sorting the entire array.

**Key takeaway:** Choosing the right data structure can significantly reduce unnecessary computation. The goal is not always to sort everything, but to process only what the problem actually requires.