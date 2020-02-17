问题：
```
给定一个整数数组（有正数有负数），找出总和最大的连续数列，并返回总和。
```
示例：
```
输入： [-2,1,-3,4,-1,2,1,-5,4]
输出： 6
解释： 连续子数组 [4,-1,2,1] 的和最大，为 6。
```
说明：
```
如果你已经实现复杂度为 O(n) 的解法，尝试使用更为精妙的分治法求解。
```
思路：
```

```
代码：
```python
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        for i in range(1, len(nums)):
            nums[i] += nums[i - 1] > 0 and nums[i - 1]
        return max(nums)
```
