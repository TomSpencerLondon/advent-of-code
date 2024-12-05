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


### Elegant solution for sorting and grouping tuples in python

The line:  
```python
distances = [abs(l - r) for l, r in zip(left_sorted, right_sorted)]
```  

### Explanation of `zip`

The `zip()` function in Python takes two or more iterables (like lists, tuples, etc.) and combines their elements into pairs. It creates an iterator of tuples, where each tuple contains one element from each iterable.

#### Example of `zip`:
```python
left_sorted = [1, 2, 3]
right_sorted = [3, 4, 5]

# Using zip
zipped = zip(left_sorted, right_sorted)
print(list(zipped))  # Output: [(1, 3), (2, 4), (3, 5)]
```

#### How it Works:
- **First Pair:** Takes the first element from `left_sorted` (1) and the first element from `right_sorted` (3), creating `(1, 3)`.
- **Second Pair:** Takes the second element from both lists, creating `(2, 4)`.
- Repeats until the shorter list is exhausted.

In this problem:
- `zip(left_sorted, right_sorted)` creates pairs of numbers from the two sorted lists. Each pair is then processed in the list comprehension to calculate the absolute difference.

---

### Why It's Elegant:
By combining `zip()` with the list comprehension, the line avoids verbose looping and manual list operations, encapsulating both **pairing** and **processing** in a single, readable statement. It’s a hallmark of Python’s design philosophy: "Simple is better than complex."

### The Zen of Python

```markdown
# The Zen of Python

The **Zen of Python** is a collection of principles that capture the philosophy behind Python's design. It encourages simplicity, readability, and elegance in code.

> "Simple is better than complex."

Here are the principles:

- Beautiful is better than ugly.
- Explicit is better than implicit.
- Simple is better than complex.
- Complex is better than complicated.
- Flat is better than nested.
- Sparse is better than dense.
- Readability counts.
- Special cases aren't special enough to break the rules.
- Although practicality beats purity.
- Errors should never pass silently.
- Unless explicitly silenced.
- In the face of ambiguity, refuse the temptation to guess.
- There should be one-- and preferably only one --obvious way to do it.
- Although that way may not be obvious at first unless you're Dutch.
- Now is better than never.
- Although never is often better than *right* now.
- If the implementation is hard to explain, it's a bad idea.
- If the implementation is easy to explain, it may be a good idea.
- Namespaces are one honking great idea -- let's do more of those!

```
[PEP 20 - The Zen of Python](https://peps.python.org/pep-0020/)
