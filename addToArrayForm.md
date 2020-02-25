问题：
```
对于非负整数 X 而言，X 的数组形式是每位数字按从左到右的顺序形成的数组。
例如，如果 X = 1231，那么其数组形式为 [1,2,3,1]。
给定非负整数 X 的数组形式 A，返回整数 X+K 的数组形式。
```
示例：
```
输入：A = [1,2,0,0], K = 34
输出：[1,2,3,4]
解释：1200 + 34 = 1234

输入：A = [2,7,4], K = 181
输出：[4,5,5]
解释：274 + 181 = 455

输入：A = [2,1,5], K = 806
输出：[1,0,2,1]
解释：215 + 806 = 1021

输入：A = [9,9,9,9,9,9,9,9,9,9], K = 1
输出：[1,0,0,0,0,0,0,0,0,0,0]
解释：9999999999 + 1 = 10000000000
```
说明：
```
1 <= A.length <= 10000
0 <= A[i] <= 9
0 <= K <= 10000
如果 A.length > 1，那么 A[0] != 0
```
思路：
```
1.A数组转为X整数
2.K+X
3.K+X转数组
```
代码：
```python
class Solution:
    def addToArrayForm(self, A: List[int], K: int) -> List[int]:
        m = 0
        sums = 0
        for i in range(len(A)-1, -1, -1):
            sums += A[i]*10**m
            m += 1
        sums += K
        sums = str(sums)
        A = []
        for x in sums:
            A.append(int(x))
        return A
```