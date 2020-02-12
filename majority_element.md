问题：
```
给定一个大小为 n 的数组，找到其中的多数元素。多数元素是指在数组中出现次数大于 ⌊ n/2 ⌋ 的元素。
你可以假设数组是非空的，并且给定的数组总是存在多数元素。
```
示例：
```
输入: [3,2,3]
输出: 3

输入: [2,2,1,1,1,2,2]
输出: 2
```
思路：
```
用哈希表来快速统计每个元素出现的次数。
用哈希表来存储每个元素，然后用一个循环在线性时间内遍历 nums ，然后我们只需要返回有最大值的键。
```
代码：
```python
class Solution:
    def majorityElement(self, nums):
        counts = collections.Counter(nums)
        return max(counts.keys(), key=counts.get)
```
