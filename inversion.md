问题：
```
给出一个 32 位的有符号整数，你需要将这个整数中每位上的数字进行反转。
```
示例：
```
输入: 123
输出: 321

输入: -123
输出: -321

输入: 120
输出: 21
```
思路：
```
对当前数取10的余数，一项项填入res尾部，res=res*10+x%10
边界情况处理：int取值[-2^31, 2^31-1] (一位符号位) 若翻转数字溢出 返回0
```
代码：
```python
class Solution:
    def reverse(self, x: int) -> int:
        if x>0:
            of = (1<<31) - 1
        else:
            of = 1<<31
        y = abs(x)
        res = 0
        while y != 0:
            res = res * 10 + y  % 10
            if(res>of):
                return 0
            y //= 10
        if(x>0):
            return res
        else:
            return -res
```
