问题：
```
给定一个二进制矩阵 A，我们想先水平翻转图像，然后反转图像并返回结果。
水平翻转图片就是将图片的每一行都进行翻转，即逆序。例如，水平翻转 [1, 1, 0] 的结果是 [0, 1, 1]。
反转图片的意思是图片中的 0 全部被 1 替换， 1 全部被 0 替换。例如，反转 [0, 1, 1] 的结果是 [1, 0, 0]。
```
示例：
```
输入: [[1,1,0],[1,0,1],[0,0,0]]
输出: [[1,0,0],[0,1,0],[1,1,1]]
解释: 首先翻转每一行: [[0,1,1],[1,0,1],[0,0,0]]；
           然后反转图片: [[1,0,0],[0,1,0],[1,1,1]]

输入: [[1,1,0,0],[1,0,0,1],[0,1,1,1],[1,0,1,0]]
输出: [[1,1,0,0],[0,1,1,0],[0,0,0,1],[1,0,1,0]]
解释: 首先翻转每一行: [[0,0,1,1],[1,0,0,1],[1,1,1,0],[0,1,0,1]]；
           然后反转图片: [[1,1,0,0],[0,1,1,0],[0,0,0,1],[1,0,1,0]]
```
说明：
```
1 <= A.length = A[0].length <= 20
0 <= A[i][j] <= 1
```
思路：
```
对于1和0的翻转，有两种思路
用 1 - 当前值，得到的就是0和1的翻转
用 1 ^ 当前值，得到的也是0和1的反转。这个符号是异或，相同为0，相异为1

In Python, the shortcut row[~i] = row[-i-1] = row[len(row) - 1 - i]helps us find the i-th value of the row, counting from the right.
对于 A[i][j]，我们将它和 A[i][c - j - 1] 进行交换（即翻转），其中 c 是数组 A 的列数。
```
代码：
```python
class Solution:
    def flipAndInvertImage(self, A: List[List[int]]) -> List[List[int]]:
        for row in A:
            for i in range((len(row) + 1) / 2):
                """
                In Python, the shortcut row[~i] = row[-i-1] = row[len(row) - 1 - i]
                helps us find the i-th value of the row, counting from the right.
                """
                row[i], row[~i] = row[~i] ^ 1, row[i] ^ 1
        return A
```
