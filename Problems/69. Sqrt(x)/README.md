# 0069. Sqrt(x)

**Platform:** LeetCode  
**Difficulty:** Easy  
**Topics:** Binary Search, Mathematics

[🔗 View Problem on LeetCode](https://leetcode.com/problems/sqrtx/)

## Problem Overview

Given a non-negative integer `x`, return the integer square root of `x`.

The result must be the **floor value** of the square root. In other words, discard the decimal part if the result is not an integer.

**Example:**
- Input: `x = 8`
- Output: `2`
- Explanation: √8 ≈ 2.828, so the integer square root is 2.

## Approach: Binary Search

Instead of checking every number from 1 to x, use Binary Search to efficiently find the integer square root.

1. Handle the base cases: if `x < 2`, return `x`.
2. Initialise the search range with `left = 2` and `right = x / 2`.
3. Calculate the middle value: `mid = left + (right - left) / 2`.
4. Calculate `mid × mid` and compare it with `x`:
   - If `mid × mid > x`, search the left half.
   - If `mid × mid < x`, search the right half.
   - If equal, return `mid`.
5. If the loop ends without an exact match, return `right`, which represents the greatest integer whose square does not exceed `x`.

This approach repeatedly halves the search space, making it significantly faster than linear searching.

## Complexity Analysis

| Complexity | Value | Explanation |
|---|---|---|
| Time | O(log x) | Binary Search halves the search space in each iteration. |
| Space | O(1) | Only a constant amount of extra memory is used. |

## Implementations

| Language | File |
|---|---|
| Python | [solution.py](./solution.py) |
| Java | [solution.java](./solution.java) |

**Implementation Note:**

In Java, `long` is used for multiplication (`(long) mid * mid`) to prevent integer overflow when calculating the square of `mid`.

Python supports arbitrary-precision integers, so the same overflow issue does not occur.

---

*Key takeaway: Binary Search can solve more than searching problems. It can also efficiently find an optimal integer value within a defined search range.*