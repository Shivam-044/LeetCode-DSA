# 0001. Two Sum

**Platform:** LeetCode  
**Difficulty:** Easy  
**Topics:** Array, Hash Table

[🔗 View Problem on LeetCode](https://leetcode.com/problems/two-sum/)

## Problem Overview

Given an array of integers `nums` and an integer `target`, find the indices of two numbers whose sum equals the target.

Return the indices of the two numbers. Each input has exactly one valid solution, and the same element cannot be used twice.

## Approach: Hash Map (One Pass)

Use a hash map to store previously visited numbers along with their indices.

1. Iterate through the array.
2. For each element, calculate its complement: `target - nums[i]`.
3. Check whether the complement already exists in the hash map.
4. If found, return the stored index and the current index.
5. Otherwise, store the current number and its index.

This approach avoids checking every possible pair and solves the problem in a single traversal.

## Complexity Analysis

| Complexity | Value | Explanation |
|---|---|---|
| Time | O(n) | Each element is visited once, with average O(1) hash map operations. |
| Space | O(n) | The hash map can store up to n elements. |

## Implementations

| Language | File |
|---|---|
| C++ | [solution.cpp](./solution.cpp) |
| Python | [solution.py](./solution.py) |

Both implementations use the same one-pass hash map approach.

---

*Key takeaway: A hash map allows us to trade extra space for faster lookups, reducing the time complexity from O(n²) to O(n) on average.*