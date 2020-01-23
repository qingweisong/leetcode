问题：
```
给定一个整数数组 nums 和一个目标值 target，请你在该数组中找出和为目标值的那 两个整数，并返回他们的数组下标。
你可以假设每种输入只会对应一个答案。但是，你不能重复利用这个数组中同样的元素。
```
示例：
```
给定 nums = [2, 7, 11, 15], target = 9
因为 nums[0] + nums[1] = 2 + 7 = 9
所以返回 [0, 1]
```
思路：
```
想判断num2 = target - num1是否也在 list 中，并返回数组下标。
1. dct['key'] = 'value'
2. 每种输入只会对应一个答案
```
代码：
```python
#遍历列表同时查字典
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        dct = {}
        for i, n in enumerate(nums):
        #判断target-num1是否在字典中.若在,返回num1 num2数组下标,若不在,将num1放入字典中 dct(num1:key).
            if target -n in dct:
                return[dct[target-n], i]
            dct[n] = i
```
