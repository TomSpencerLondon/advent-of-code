# notebooks-algorithms

### Problem Summary: Advent of Code - Day 1: Historian Hysteria

### Simple Summary:

The Chief Historian is missing, and the Elves are trying to find him by checking locations he might have visited. Each location has a unique number (a location ID), and the Elves found two lists of these numbers in his office.

### Problem Description
The two lists of location IDs don't match. The task is to help The Historians reconcile the lists.

#### Example Input

**Left List**:
```
3
4
2
1
3
3
```

**Right List**:
```
4
3
5
3
9
3
```

#### Goal:
Given your puzzle input (actual lists of location IDs), calculate and return the **total distance**.

### Explanation and Purpose:

This section explains how to calculate the "total distance" between two lists of numbers. The idea is to compare the two lists in a systematic way to measure how different they are.

---
#### Statement

Maybe the lists are only off by a small amount! To find out, pair up the numbers and measure how far apart they are. Pair up the smallest number in the left list with the smallest number in the right list, then the second-smallest left number with the second-smallest right number, and so on.


### **What Does It Mean?**
1. **Pairing Numbers:** 
   - Sort both lists in ascending order.
   - Match the smallest number in the first list with the smallest number in the second list, the second smallest with the second smallest, and so on.

2. **Calculating Differences:**
   - For each pair, calculate the absolute difference between the two numbers. For example:
     - If you pair `3` from the left list with `7` from the right list, the difference is `|3 - 7| = 4`.

3. **Summing Differences:**
   - Add up all the differences across all pairs to get the **total distance**.

---

### **How Is It Helpful?**
This process:
- Provides a numerical measure of how "different" the two lists are.
- Helps to reconcile the lists by quantifying the gap between corresponding items.

---

### **Example Breakdown:**
Given the lists:
- **Left List**: `[3, 4, 2, 1, 3, 3]`
- **Right List**: `[4, 3, 5, 3, 9, 3]`

#### Step-by-Step Process:
1. **Sort Both Lists:**
   - Left: `[1, 2, 3, 3, 3, 4]`
   - Right: `[3, 3, 3, 4, 5, 9]`

2. **Pair Numbers by Position in Sorted Lists:**
   - Pair 1: `(1, 3)` → Difference = `|1 - 3| = 2`
   - Pair 2: `(2, 3)` → Difference = `|2 - 3| = 1`
   - Pair 3: `(3, 3)` → Difference = `|3 - 3| = 0`
   - Pair 4: `(3, 4)` → Difference = `|3 - 4| = 1`
   - Pair 5: `(3, 5)` → Difference = `|3 - 5| = 2`
   - Pair 6: `(4, 9)` → Difference = `|4 - 9| = 5`

3. **Sum the Differences:**
   - Total Distance = `2 + 1 + 0 + 1 + 2 + 5 = 11`

---

This "distance" value provides insight into how similar or dissimilar the two lists are, which might help prioritize or reconcile differences when searching for the missing Chief Historian.
