问题：
```
给你一个非递减的 有序 整数数组，已知这个数组中恰好有一个整数，它的出现次数超过数组元素总数的 25%。
请你找到并返回这个整数
```
示例：
```
输入：arr = [1,2,2,6,6,6,6,7,10]
输出：6
```
提示：
```
1 <= arr.length <= 10^4
0 <= arr[i] <= 10^5
```
思路：
```
用整数运算 count * 4 > arr.length 代替浮点数运算 count > arr.length * 25%，减少精度误差。
```
代码：
```python
class Solution:
    def findSpecialInteger(self, arr: List[int]) -> int:
        n = len(arr)
        cur, cnt = arr[0], 0
        for i in range(n):
            if arr[i] == cur:
                cnt += 1
                if cnt * 4 > n:
                    return cur
            else:
                cur, cnt = arr[i], 1
        return -1
```
