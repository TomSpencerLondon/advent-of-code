# notebooks-algorithms

### Problem Summary: Advent of Code - Day 1: Historian Hysteria

The goal is to help a group of Elvish Senior Historians reconcile two lists of **location IDs** to assist in locating the missing Chief Historian.

#### Steps to Solve:
1. **Input**: Two lists of integers (location IDs).
2. **Task**: 
   - Sort both lists in ascending order.
   - Pair up integers by their sorted order (smallest to smallest, second smallest to second smallest, etc.).
   - Compute the absolute difference between each pair.
   - Sum up all the absolute differences to find the **total distance**.
3. **Output**: The total distance between the two lists.

#### Example:
For the input lists:
- Left List: `[3, 4, 2, 1, 3, 3]`
- Right List: `[4, 3, 5, 3, 9, 3]`

Steps:
- Sort the lists:
  - Left: `[1, 2, 3, 3, 3, 4]`
  - Right: `[3, 3, 3, 4, 5, 9]`
- Pair and calculate distances:
  - `(1, 3)` → `|1 - 3| = 2`
  - `(2, 3)` → `|2 - 3| = 1`
  - `(3, 3)` → `|3 - 3| = 0`
  - `(3, 4)` → `|3 - 4| = 1`
  - `(3, 5)` → `|3 - 5| = 2`
  - `(4, 9)` → `|4 - 9| = 5`
- Total Distance: `2 + 1 + 0 + 1 + 2 + 5 = 11`

#### Goal:
Given your puzzle input (actual lists of location IDs), calculate and return the **total distance**.
