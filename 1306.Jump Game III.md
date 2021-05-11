---
title: 1306. Jump Game III
tags: Leetcode,2021
---
# 【LeetCode】1306.Jump Game III 
## Description
>Given an array of non-negative integers arr, you are initially positioned at start index of the array. When you are at index i, you can jump to i + arr[i] or i - arr[i], check if you can reach to any index with value 0.

>Notice that you can not jump outside of the array at any time.

 
## Example
```
Example 1:

Input: arr = [4,2,3,0,3,1,2], start = 5
Output: true
Explanation: 
All possible ways to reach at index 3 with value 0 are: 
index 5 -> index 4 -> index 1 -> index 3 
index 5 -> index 6 -> index 4 -> index 1 -> index 3 
Example 2:

Input: arr = [4,2,3,0,3,1,2], start = 0
Output: true 
Explanation: 
One possible way to reach at index 3 with value 0 is: 
index 0 -> index 4 -> index 1 -> index 3
Example 3:

Input: arr = [3,0,2,1,2], start = 2
Output: false
Explanation: There is no way to reach at index 1 with value 0.
 
```

## Constraints:

```
1 <= arr.length <= 5 * 104
0 <= arr[i] < arr.length
0 <= start < arr.length
```
## Code
```
public class Solution {
   public bool CanReach(int[] arr, int start)
        {
            Queue<int> bfs = new Queue<int>();
            ISet<int> visited = new HashSet<int>();

            bfs.Enqueue(start);
            visited.Add(start);

            while (bfs.Count > 0)
            {
                var idx = bfs.Dequeue();
                if (arr[idx] == 0)
                {
                    return true;
                }

                var newIdx = idx + arr[idx];
                if (newIdx >= 0 && newIdx < arr.Length && visited.Add(newIdx))
                {
                    bfs.Enqueue(newIdx);
                }

                newIdx = idx - arr[idx];
                if (newIdx >= 0 && newIdx < arr.Length && visited.Add(newIdx))
                {
                    bfs.Enqueue(newIdx);
                }
            }

            return false;
        }
}
```