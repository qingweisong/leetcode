问题：
```
给定一个非空数组，返回此数组中第三大的数。如果不存在，则返回数组中最大的数。要求算法时间复杂度必须是O(n)。
```
示例：
```
示例 1:

输入: [3, 2, 1]
输出: 1

解释: 第三大的数是 1.
示例 2:

输入: [1, 2]
输出: 2

解释: 第三大的数不存在, 所以返回最大的数 2 .
示例 3:

输入: [2, 2, 3, 1]
输出: 1

解释: 注意，要求返回第三大的数，是指第三大且唯一出现的数。
存在两个值为2的数，它们都排第二。
```
思路：
```
1 用first, second, third分别保存最大，次大和第三大的数，初始时设为负无穷
2 遍历数组，并将其与first,second,third比较，判断是否需要更新
3 根据最终的first，second，third返回结果
```
代码：
```python
class Solution:
    def thirdMax(self, nums: List[int]) -> int:
        first = -float('inf')
        second = -float('inf')
        third = -float('inf')
        for num in nums:
            if num > first:
                first, second, third = num, first, second
            elif num == first:
                continue
            elif num > second:
                second, third = num, second
            elif num == second:
                continue
            elif num > third:
                third = num
            else:
                pass
        if third != -float('inf'):
            return third
        else:
            return first
```
