问题：
```
给定一个按非递减顺序排序的整数数组 A，返回每个数字的平方组成的新数组，要求也按非递减顺序排序。
```
示例：
```
输入：[-4,-1,0,3,10]
输出：[0,1,9,16,100]

输入：[-7,-3,2,3,11]
输出：[4,9,9,49,121]
```
提示：
```
1. 1 <= A.length <= 10000
2. -10000 <= A[i] <= 10000
3. A已按非递减顺序排序。
```
思路：
```
创建一个新的数组
每个元素是给定数组对应位置元素的平方
然后排序这个数组。
```
代码：
```python
class Solution(object):
    def sortedSquares(self, A):
        #sorted()返回列表
        return sorted(x*x for x in A)
```
