问题：
```
数组nums包含从0到n的所有整数，但其中缺了一个。请编写代码找出那个缺失的整数。你有办法在O(n)时间内完成吗？
```
示例：
```
输入：[3,0,1]
输出：2
 
输入：[9,6,4,2,3,5,7,0,1]
输出：8
```
说明：
```
1 <= A.length = A[0].length <= 20
0 <= A[i][j] <= 1
```
思路：
```
0到n的和减去数组和
```
代码：
```python
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        return len(nums)*(len(nums)+1)//2-sum(nums)
```
