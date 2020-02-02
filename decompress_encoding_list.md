问题：
```
给你一个以行程长度编码压缩的整数列表 nums。
考虑每对相邻的两个元素 [a, b] = [nums[2*i], nums[2*i+1]] （其中 i >= 0 ），每一对都表示解压后有 a 个值为 b 的元素
请你返回解压后的列表。
```
示例：
```
输入：nums = [1,2,3,4]
输出：[2,4,4,4]
解释：第一对 [1,2] 代表着 2 的出现频次为 1，所以生成数组 [2]。
第二对 [3,4] 代表着 4 的出现频次为 3，所以生成数组 [4,4,4]。
最后将它们串联到一起 [2] + [4,4,4] = [2,4,4,4]。
```
说明：
```
2 <= nums.length <= 100
nums.length % 2 == 0
1 <= nums[i] <= 100
```
思路：
```
解码nums前2个元素 + 解码2个元素后面的元素，使用递归解决。
使用try跳过nums[2:]不存在的情况。
```
代码：
```python
class Solution:
    def decompressRLElist(self, nums: List[int]) -> List[int]:
        res = nums[0] * [nums[1]]
        try:
            res.extend(self.decompressRLElist(nums[2:]))
        except:
            pass
        return res
```
