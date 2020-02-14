问题：
```
实现一个算法，确定一个字符串 s 的所有字符是否全都不同。
```
示例：
```
输入: s = "leetcode"
输出: false 

输入: s = "abc"
输出: true
```
说明：
```
0 <= len(s) <= 100
如果你不使用额外的数据结构，会很加分。
```
思路：
```
len({*astr}) 字符串中不同字符的长度与字符串总长度是否相等
```
代码：
```python
class Solution:
    def isUnique(self, astr: str) -> bool:
        return len({*astr}) == len(astr)
```
