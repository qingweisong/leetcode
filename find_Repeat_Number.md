问题：
```
找出数组中重复的数字。
在一个长度为 n 的数组 nums 里的所有数字都在 0～n-1 的范围内。数组中某些数字是重复的，但不知道有几个数字重复了，也不知道每个数字重复了几次。请找出数组中任意一个重复的数字。
```
示例：
```
输入：
[2, 3, 1, 0, 2, 5, 3]
输出：2 或 3 
```
说明：
```
2 <= n <= 100000
```
思路：
```
寻找数组中的重复数字，直接想到的方法是遍历数组，并使用 HashMap 统计每个数字的数量，遇到数量大于1的数字则返回。
```
代码：
```python
class Solution:
    def findRepeatNumber(self, nums: [int]) -> int:
        i = 0
        while i < len(nums):
            if nums[i] == i:
                i += 1
                continue
            if nums[nums[i]] == nums[i]: return nums[i]
            nums[nums[i]], nums[i] = nums[i], nums[nums[i]]
        return -1
```
