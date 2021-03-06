问题：
```
给你一个单链表的引用结点 head。链表中每个结点的值不是 0 就是 1。已知此链表是一个整数数字的二进制表示形式。
请你返回该链表所表示数字的 十进制值 。
```
示例：

![](https://assets.leetcode-cn.com/aliyun-lc-upload/uploads/2019/12/15/graph-1.png)
```
输入：head = [1,0,1]
输出：5
解释：二进制数 (101) 转化为十进制数 (5)

输入：head = [0]
输出：0

输入：head = [1]
输出：1

输入：head = [1,0,0,1,0,0,1,1,1,0,0,0,0,0,0]
输出：18880

输入：head = [0,0]
输出：0
```
提示：
```
链表不为空。
链表的结点总数不超过 30。
每个结点的值不是 0 就是 1。
```
思路：
```
链表中从高位到低位存放了数字的二进制表示
使用二进制转十进制的方法，在遍历一遍链表的同时得到数字的十进制值。
```
代码：
```python
class Solution:
    def getDecimalValue(self, head: ListNode) -> int:
        cur = head
        ans = 0
        while cur:
            ans = ans * 2 + cur.val
            cur = cur.next
        return ans
```
