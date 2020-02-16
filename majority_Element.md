问题：
```
如果数组中多一半的数都是同一个，则称之为主要元素。给定一个整数数组，找到它的主要元素。若没有，返回-1。
```
示例：
```
输入：[1,2,5,9,5,9,5,5,5]
输出：5

输入：[3,2]
输出：-1

输入：[2,2,1,1,1,2,2]
输出：2
```
说明：
```
你有办法在时间复杂度为 O(N)，空间复杂度为 O(1) 内完成吗？
```
思路：
```
先排序，然后查询mid处的值是否在数组中出现次数超过一半
```
代码：
```python
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        length = len(nums)
        nums.sort()
        mid = length // 2
        tmp = nums[mid]
        if nums.count(tmp) > mid:
            return nums[mid]
        else:
            return -1
```
