问题：
```
给定一组不含重复元素的整数数组 nums，返回该数组所有可能的子集（幂集）。
```
示例：
```
输入: nums = [1,2,3]
输出:
[
  [3],
  [1],
  [2],
  [1,2,3],
  [1,3],
  [2,3],
  [1,2],
  []
]
```
提示：
```
解集不能包含重复的子集。
```
思路：
```

```
代码：
```python
class Solution:
    def subsets(self, nums: List[int]) -> List[List[int]]:
        res = []
        n = len(nums)
        nums.sort()
        def helper(idx, tmp):
            res.append(tmp)
            for i in range(idx, n):

                helper(i + 1, tmp + [nums[i]])
        helper(0, [])
        return res
```
