问题：
```
给定一个矩阵 A， 返回 A 的转置矩阵。
矩阵的转置是指将矩阵的主对角线翻转，交换矩阵的行索引与列索引。
```
示例：
```
输入：[[1,2,3],[4,5,6],[7,8,9]]
输出：[[1,4,7],[2,5,8],[3,6,9]]

输入：[[1,2,3],[4,5,6]]
输出：[[1,4],[2,5],[3,6]]
```
提示：
```
1 <= A.length <= 1000
1 <= A[0].length <= 1000
```
思路：
```
R x C 的矩阵 A 转置后会得到尺寸为 C x R 的矩阵 ans，ans[c][r] = A[r][c]。
初始化一个新的矩阵 ans 来表示答案
```
代码：
```python
class Solution(object):
    def transpose(self, A):
        R, C = len(A), len(A[0])
        ans = [[None] * R for _ in xrange(C)]
        for r, row in enumerate(A):
            for c, val in enumerate(row):
                ans[c][r] = val
        return ans
```
