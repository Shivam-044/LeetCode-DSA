# 0002. Add Two Numbers

**Platform:** LeetCode  
**Difficulty:** Medium  
**Topics:** Linked List, Mathematics, Recursion

[🔗 View Problem on LeetCode](https://leetcode.com/problems/add-two-numbers/)

## Problem Overview

Given two non-empty linked lists representing two non-negative integers, add the numbers and return their sum as a linked list.

The digits are stored in **reverse order**, with each node containing a single digit.

The result must also be represented in reverse order.

**Example:**

- Input: `l1 = [2, 4, 3]`, `l2 = [5, 6, 4]`
- Output: `[7, 0, 8]`
- Explanation: 342 + 465 = 807.

## Approach: Iterative Addition with Carry

Traverse both linked lists simultaneously and perform digit-by-digit addition, similar to traditional elementary addition.

Since the digits are stored in reverse order, addition can begin directly from the head nodes without reversing either list.

### Algorithm

1. Create a dummy node to simplify construction of the result linked list.
2. Maintain a pointer `curr` to track the last node of the result.
3. Initialise `carry = 0`.
4. Traverse both lists while either list has remaining nodes or a carry still exists.
5. Extract the current digits from both lists. If a list has ended, use `0` as its digit.
6. Calculate the total by adding both digits and the carry.
7. Update the carry using integer division by 10.
8. Calculate the current result digit using modulo 10.
9. Create a new node containing that digit and append it to the result list.
10. Move to the next nodes in both input lists.
11. Return `dummy.next`, which points to the actual result list.

### Example Walkthrough

```text
List 1:  2 → 4 → 3
List 2:  5 → 6 → 4
         ─────────
Sum:     7 → 0 → 8
```

| Position | Digit 1 | Digit 2 | Carry In | Total | Result Digit | Carry Out |
|---|---:|---:|---:|---:|---:|---:|
| 1 | 2 | 5 | 0 | 7 | 7 | 0 |
| 2 | 4 | 6 | 0 | 10 | 0 | 1 |
| 3 | 3 | 4 | 1 | 8 | 8 | 0 |

The resulting linked list represents `807`, stored in reverse order as `[7, 0, 8]`.

## Key Implementation Concepts

**1. Dummy Node**

A temporary node placed before the result list. It simplifies node insertion and avoids special handling for the first result node.

**2. Carry Propagation**

The carry stores the overflow from the previous digit addition and is included in the next calculation.

**3. Handling Unequal List Lengths**

When one list ends before the other, its missing digit is treated as `0`. This allows both lists to be processed in a single traversal.

**4. Final Carry Handling**

The loop continues even after both input lists end if a carry remains. This ensures that an additional digit is not lost.

## Complexity Analysis

Let `m` and `n` represent the lengths of the two input linked lists.

| Complexity | Value | Explanation |
|---|---|---|
| Time | O(max(m, n)) | Each input node is visited exactly once. |
| Auxiliary Space | O(1) | Only a constant number of pointers and variables are used, excluding the output list. |
| Output Space | O(max(m, n) + 1) | New nodes are created for the resulting digits, including a possible final carry. |

## Implementations

| Language | Approach | File |
|---|---|---|
| Java | Iterative Addition with Carry | [Solution.java](./Solution.java) |
| Python | Iterative Addition with Carry | [Solution.py](./Solution.py) |

Both implementations follow the same algorithm, use a dummy node to construct the result, and create a new linked list without modifying the input lists.

---

*Key takeaway: A dummy node simplifies linked-list construction, while carry propagation allows arithmetic operations to be performed efficiently without converting the linked lists into complete integer values.*
