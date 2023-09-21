# leet-day69

# Median of Two Sorted Arrays

This problem involves finding the median of two sorted arrays. Given two sorted arrays, `nums1` and `nums2`, with lengths `m` and `n` respectively, the task is to find the median of the combined sorted array of both arrays. The overall time complexity of the solution should be O(log(min(m, n))).

## Problem Statement

Given two sorted arrays `nums1` and `nums2`, return the median of the two arrays.

## Example

### Input

```python
nums1 = [1, 3]
nums2 = [2]
```

### Output

```python
2.00000
```

Explanation: The merged array is `[1, 2, 3]`, and the median is 2.

## Constraints

- `nums1.length == m`
- `nums2.length == n`
- `0 <= m <= 1000`
- `0 <= n <= 1000`
- `1 <= m + n <= 2000`
- `-106 <= nums1[i], nums2[i] <= 106`

## Approach

The problem can be solved using a binary search algorithm. The key idea is to partition both arrays into two parts such that the elements on the left side are smaller than the elements on the right side. This ensures that the median is at the boundary of these two parts.

1. Choose the smaller array as `nums1` to reduce the time complexity.
2. Use binary search on the smaller array (`nums1`) to find the correct partition.
3. Calculate the partition indices for both arrays based on the binary search.
4. Find the maximum element on the left side and the minimum element on the right side.
5. Calculate the median based on the length of the combined arrays and the maximum and minimum elements.

## Pseudocode

```python
1. If nums1 is longer than nums2, swap them to ensure nums1 is shorter.
2. Set m to the length of nums1 and n to the length of nums2.
3. Initialize variables left = 0, right = m, and halfLen = (m + n + 1) / 2.
4. Use a while loop with the condition left <= right to perform binary search.
    a. Calculate partition1 as (left + right) / 2.
    b. Calculate partition2 as halfLen - partition1.
    c. Calculate maxLeft1, minRight1, maxLeft2, and minRight2 based on partition indices.
    d. Check if maxLeft1 <= minRight2 and maxLeft2 <= minRight1.
        - If true, calculate the median based on even or odd length.
        - If false, adjust the binary search window accordingly.
5. If the while loop exits without finding a median, throw an exception (input arrays are not sorted).
```

## Complexity Analysis

The binary search approach has a time complexity of O(log(min(m, n))) since we are reducing the search space in each iteration.

## Implementation

You can implement this algorithm in your preferred programming language, such as C++, Python, Java, etc.
