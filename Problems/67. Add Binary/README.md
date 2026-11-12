# 0067. Add Binary

**Platform:** LeetCode  
**Difficulty:** Easy  
**Topics:** String, Mathematics, Binary Arithmetic

[🔗 View Problem on LeetCode](https://leetcode.com/problems/add-binary/)

## Problem Overview

Given two binary strings `a` and `b`, return their sum as a binary string.

The result must be represented in base 2 rather than decimal.

**Example:**
- Input: `a = "1010"`, `b = "1011"`
- Output: `"10101"`
- Explanation: 10 + 11 = 21, and 21 in binary is `10101`.

## Approach 1: Built-in Binary Conversion (Python)

Use Python's built-in functions to convert binary strings into integers, perform addition, and convert the result back into binary.

1. Convert both binary strings into integers using `int(value, 2)`.
2. Add the converted integers.
3. Convert the sum into binary using `bin()`.
4. Remove the `0b` prefix using `[2:]`.

**Key Functions:**
- `int(value, 2)` – Converts a binary string into an integer.
- `bin(value)` – Returns the binary representation of an integer.

## Approach 2: Manual Binary Addition (Java)

Perform binary addition digit by digit using the carry mechanism, similar to conventional decimal addition.

1. Initialise two pointers at the last positions of both strings.
2. Start with `carry = 0`.
3. Traverse both strings from right to left.
4. Add the current digits and carry.
5. Append `sum % 2` to the result.
6. Update the carry using `sum / 2`.
7. Continue until both strings are exhausted and no carry remains.
8. Reverse the result to obtain the correct binary representation.

**Binary Addition Rules:**

| Addition | Result | Carry |
|---|---:|---:|
| 0 + 0 | 0 | 0 |
| 0 + 1 | 1 | 0 |
| 1 + 0 | 1 | 0 |
| 1 + 1 | 0 | 1 |
| 1 + 1 + 1 | 1 | 1 |

**Key Concepts:**
- `StringBuilder` – Efficiently builds the result.
- `sum % 2` – Determines the current binary digit.
- `sum / 2` – Determines the next carry.
- `reverse()` – Restores the correct digit order.

## Complexity Analysis

Let `n` and `m` represent the lengths of the two input strings.

| Implementation | Time Complexity | Space Complexity |
|---|---|---|
| Python (Built-in Conversion) | O(n + m) | O(n + m) |
| Java (Manual Addition) | O(n + m) | O(n + m) |

**Explanation:**
- Python performs binary conversion, integer addition, and result conversion.
- Java processes each digit once and constructs the result using `StringBuilder`.
- Both approaches require additional space for the resulting binary representation.

## Implementations

| Language | Approach | File |
|---|---|---|
| Python | Built-in Binary Conversion | [solution.py](./Solution.py) |
| Java | Manual Addition with Carry | [solution.java](./Solution.java) |

---

*Key takeaway: Built-in functions simplify implementation, but understanding carry propagation reveals the underlying arithmetic. Knowing both approaches makes problem-solving more versatile.*
