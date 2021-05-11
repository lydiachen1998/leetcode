---
title:  1.Two Sum
tags: Leetcode,2021
---
# 【LeetCode】 1. Two Sum
## Description
>Given an array of integers, return indices of the two numbers such that they add up to a specific target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.

>給予一整數陣列，請回傳陣列中兩個索引值，其值相加等於目標值。
你可以假設陣列中只會有一個解，不需要考慮有兩種或以上的情況。

## Example:
>Given nums = [2, 7, 11, 15], target = 9,
Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
Solution
使用hash table的做法加速，只需要跑一次for loop即可解決。
以測資為例，第一個遇到2且目標為9，將第7(9-2)格放入0，意思是之後遇到7時，去找第7格就知道要跟哪一格相加了。
## Code
```
public class Solution {
    public int[] TwoSum(int[] nums, int target) {
        
      
          if(nums == null || nums.Length < 2)
            return new int[2];
        Dictionary<int,int> dic = new Dictionary<int,int>();
        
        for(int i = 0; i < nums.Length; i++)
        {
            if(dic.ContainsKey(target - nums[i]))
                return new int[]{i, dic[target - nums[i]]};
            else if(!dic.ContainsKey(nums[i]))
                dic.Add(nums[i], i);
        }
        
        return new int[2];
    }
}
```
### tags: LeetCode C#