---
title: 35.Search Insert Position
tags: Leetcode,2021
---
# 【LeetCode】35. Search Insert Position
## Description
>Given a sorted array and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.
You may assume no duplicates in the array.

>給一個排序過的陣列和一個目標數字，如果目標在陣列中，回傳它的索引值；否則請回傳它應該被插入的位置。

## Example:
```
Example 1:

Input: [1,3,5,6], 5
Output: 2


Example 2:

Input: [1,3,5,6], 2
Output: 1


Example 3:

Input: [1,3,5,6], 7
Output: 4


Example 4:

Input: [1,3,5,6], 0
Output: 0
```
## Solution

## Constraints:

```
1 <= nums.length <= 104
-104 <= nums[i] <= 104
nums contains distinct values sorted in ascending order.
-104 <= target <= 104
```
## Code
```
public class Solution {
    public int SearchInsert(int[] nums, int target) {
         if (nums == null || nums.Length == 0)
            return -1;
        
        int i = 0,
            j = nums.Length - 1;
        
        while (i <= j)
        {
            int m = j + (i - j) / 2;
            
            if (nums[m] == target)
                return m;
            else if (nums[m] < target)
                i = m + 1;
            else
                j = m - 1;
        }
        
        return i;
    
    }
}
```