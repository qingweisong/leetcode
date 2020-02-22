问题：
```
给你一个 m * n 的矩阵 grid，矩阵中的元素无论是按行还是按列，都以非递增顺序排列。 
请你统计并返回 grid 中 负数 的数目。
```
示例：
```
输入：grid = [[4,3,2,-1],[3,2,1,-1],[1,1,-1,-2],[-1,-1,-2,-3]]
输出：8
解释：矩阵中共有 8 个负数。

输入：grid = [[3,2],[1,0]]
输出：0

输入：grid = [[1,-1],[-1,-1]]
输出：3

输入：grid = [[-1]]
输出：1
```
说明：
```
m == grid.length
n == grid[i].length
1 <= m, n <= 100
-100 <= grid[i][j] <= 100
```
思路：
```
用二层循环遍历矩阵中的每一个元素
在查找到负数时，
用矩阵的列数n减去当前查找到的负数所在的列数j，
并跳出此次列循环
```
代码：
```python
class Solution:
    def countNegatives(self, grid: List[List[int]]) -> int:
        neg = 0
        m = len(grid)#行
        n = len(grid[0])#列
        for i in range(0,m):
            for j in range(0,n):
                if grid[i][j] < 0:
                    neg = neg + (n-j)
                    break
        return neg
```
