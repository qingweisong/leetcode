问题：
```
编写一种算法，若M × N矩阵中某个元素为0，则将其所在的行与列清零。
```
示例：
```
输入：
[
  [1,1,1],
  [1,0,1],
  [1,1,1]
]
输出：
[
  [1,0,1],
  [0,0,0],
  [1,0,1]
]

输入：
[
  [0,1,2,0],
  [3,4,5,2],
  [1,3,1,5]
]
输出：
[
  [0,0,0,0],
  [0,4,5,0],
  [0,3,1,0]
]
```
思路：
```
先将 n - 1 个自然数 0, 1, 2, ..., n - 2 放入数组中，它们的和为 sum。
对于剩下的 1 个数，令其为 -sum，此时这 n 个数的和为 0
```
代码：
```python
class Solution:
    def setZeroes(self, matrix: List[List[int]]) -> None:
        """
        Do not return anything, modify matrix in-place instead.
        """
        m = len(matrix)
        n = len(matrix[0])
        # 记录0的坐标
        temp = []
        for i in range(m):
            for j in range(n):
                if matrix[i][j] == 0:
                    temp.append((i,j))

        for i,j in temp:
            for k in range(m): 
                # 所在列设全0
                matrix[k][j] = 0
            for l in range(n):
                # 所在行设全0
                matrix[i][l] = 0

        return matrix
```
