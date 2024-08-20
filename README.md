# Daily Solve Problems

This repository contains C++ solutions for daily coding problems of My Learnings.
## Overview

- **Language**: C++
- **Purpose**: Practice and improve coding skills by solving daily problems from various platforms.
- **Structure**: Each solution is contained within a C++ class, following standard conventions.

## Problem 1: Find the Index of the First Occurrence in a String

- **Platform**: [LeetCode](https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/?envType=study-plan-v2&envId=top-interview-150)
- **Difficulty**: Easy/Medium
- **Solution**: A C++ implementation to find the first occurrence of a substring within a string.

### Solution Explanation

The problem is to find the first occurrence of the substring `needle` in the string `haystack`. If `needle` is found, return its index; otherwise, return `-1`.

**Key Points**:
- **Edge Cases**: Consider cases where `haystack` is smaller or equal in length to `needle`.
- **Substr Function**: The solution uses the `substr` function to compare parts of the `haystack` with `needle`.

### Code Implementation

```cpp
class Solution {
public:
    int strStr(string h, string n) {
        int k = n.size();

        if (h.size() < k) return -1;

        if (h.size() == k) {
            return h == n ? 0 : -1;
        }

        string str = h.substr(0, k);
        int l = 0;

        while ((l + k) <= h.size()) {
            str = h.substr(l, k);
            if (str == n) {
                return l;
            }
            l++;
        }

        return -1;
    }
};
