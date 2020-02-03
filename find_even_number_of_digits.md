问题：
```
给你一个整数数组 nums，请你返回其中位数为 偶数 的数字的个数。
```
示例：
```
输入：nums = [12,345,2,6,7896]
输出：2

输入：nums = [555,901,482,1771]
输出：1 
```
提示：
```
1 <= nums.length <= 500
1 <= nums[i] <= 10^5
```
思路：
```
枚举数组 nums 中的整数，并依次判断每个整数 num是否包含偶数个数字。
使用语言内置的整数转字符串函数，将 num 转换为字符串后，判断其长度是否为偶数即可
```
代码：
```python
class Solution:
    def findNumbers(self, nums: List[int]) -> int:
        return sum(1 for num in nums if len(str(num)) % 2 == 0)
        #return sum(len(str(num)) % 2 == 0 for num in nums)
```
