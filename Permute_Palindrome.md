问题：
```
给定一个字符串，编写一个函数判定其是否为某个回文串的排列之一。
回文串是指正反两个方向都一样的单词或短语。排列是指字母的重新排列。
回文串不一定是字典当中的单词。
```
示例：
```
输入："tactcoa"
输出：true（排列有"tacocat"、"atcocta"，等等）
```
思路：
```
将字符串存入哈希表，再计算每个字符奇数个的个数，如果奇数个数大于2个，就判定False
```
代码：
```python
class Solution:
class Solution(object):
    def canPermutePalindrome(self, s):
        """
        :type s: str
        :rtype: bool
        """
        #用哈希表
        h = {}
        k = 0
        for i in s:
            if i not in h.keys():
                h[i] = 0
            else:
                h[i] += 1
        #print(h)
        for j in h.values():
            #print(j)
            if (j % 2) == 0:
                k += 1
        #print(k)
        if k > 1:
            return False
        else:
            return True
```
