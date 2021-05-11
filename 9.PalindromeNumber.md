---
title: 9.Palindrome Number
tags: Leetcode,2021
---
# 【LeetCode】 9. Palindrome Number
## Description

>Determine whether an integer is a palindrome. An integer is a palindrome when it reads the same backward as forward.

>判斷一個數字是不是回文。回文指前唸到後和後唸到前一樣。

Example:
Example 1:
Input: 121
Output: true

```
Example 2:
Input: -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.

Example 3:
Input: 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
```
## Solution

## Code
```
public class Solution {
    public bool IsPalindrome(int x) {
         if(x < 0)
            {
                return false;
            }

            if(x == 0)
            {
                return true;
            }

            int left = (int) Math.Floor(Math.Log10(x));
            int right = 0;

            while (left >= right)
            {
                int leftDigit = (x / ((int) Math.Pow(10, left--))) % 10;
                int rightDigit = (x / ((int)Math.Pow(10, right++))) % 10;

                if (leftDigit != rightDigit)
                {
                    return false;
                }
            }

            return true;
        
    }
}
```