问题：
```
在一个 m*n 的棋盘的每一格都放有一个礼物，每个礼物都有一定的价值（价值大于 0）。
你可以从棋盘的左上角开始拿格子里的礼物，并每次向右或者向下移动一格、直到到达棋盘的右下角。
给定一个棋盘及其上面的礼物的价值，请计算你最多能拿到多少价值的礼物？
```
示例：
```
输入: 
[
  [1,3,1],
  [1,5,1],
  [4,2,1]
]
输出: 12
解释: 路径 1→3→5→2→1 可以拿到最多价值的礼物
```
限制：
```
0 < grid.length <= 200
0 < grid[0].length <= 200
```
思路：
```
动态规划
```
代码：
```python
class Solution:
    def maxValue(self, grid: List[List[int]]) -> int:
        m, n = len(grid), len(grid[0])
        #构建一个m行n列的空矩阵
        dp = [[None] * n for _ in range(m)]
        dp[0][0] = grid[0][0]
        # 第一行
        for col in range(1, n):
            dp[0][col] = dp[0][col-1] + grid[0][col]
        # 第一列
        for row in range(1, m):
            dp[row][0] = dp[row-1][0] + grid[row][0]
        # 其他部分
        for row in range(1, m):
            for col in range(1, n):
                dp[row][col] = grid[row][col] + max(dp[row-1][col], dp[row][col-1])
        return dp[m-1][n-1
```
