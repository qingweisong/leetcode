问题：
```
输入一个字符串，打印出该字符串中字符的所有排列。
你可以以任意顺序返回这个字符串数组，但里面不能有重复元素。
```
示例：
```
输入：s = "abc"
输出：["abc","acb","bac","bca","cab","cba"]
```
限制：
```
1 <= s 的长度 <= 8
```
思路：
```
字符串的全排列
```
代码：
```python
class Solution:
    def permutation(self, s: str) -> List[str]:
        if not s: return 
        s=list(sorted(s))
        res=[]
        def helper(s,tmp):
            if not s: res.append(''.join(tmp))
            for i,char in enumerate(s):
                if i>0 and s[i]==s[i-1]:
                    continue
                helper(s[:i]+s[i+1:],tmp+[char])
        helper(s,[])
        return res
```
