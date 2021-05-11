---
title: 7.Reverse Integer
tags: Leetcode,2021
---
# 【LeetCode】 7. Reverse Integer
## Description
>Given a 32-bit signed integer, reverse digits of an integer.

>給一個32位元的有號數，請反轉該數字的每個位數。

```
Example:
Example 1:
Input: 123
Output: 321

Example 2:
Input: -123
Output: -321

Example 3:
Input: 120
Output: 21
```
## Solution
>用%10把最低位元拿出來，用*10將每一位元推到下一位。
如果反轉後有溢位發生，直接輸出零。
## Code
```
public class Solution {
    public int Reverse(int x) {
        bool pos = x >= 0;
        long res = 0;
        x = pos ? x : -x;
        while (x != 0) {
            res = res * 10 + (x % 10);
            x /= 10;
        }
        return (res <= Math.Pow(-2, 31) || res >= Math.Pow(2, 31) - 1) ? 0: pos ? (int) res: (int) -res;
    }
}
```
tags: LeetCode C#
