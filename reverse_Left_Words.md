问题：
```
字符串的左旋转操作是把字符串前面的若干个字符转移到字符串的尾部。请定义一个函数实现字符串左旋转操作的功能。
比如，输入字符串"abcdefg"和数字2，该函数将返回左旋转两位得到的结果"cdefgab"。
```
示例：
```
输入: s = "abcdefg", k = 2
输出: "cdefgab"

输入: s = "lrloseumgh", k = 6
输出: "umghlrlose"
```
说明：
```
1 <= k < s.length <= 10000
```
思路：
```
将s + s 形成一个两倍长度的字符串， 这样s[k:n + k] 就是我们要求的结果
```
代码：
```python
class Solution:
    def reverseLeftWords(self, s: str, k: int) -> str:
        n = len(s)
        s = s + s
        return s[k:n + k]
```
