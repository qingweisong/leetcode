问题：
```
反转一个单链表。
```
示例：
```
输入: 1->2->3->4->5->NULL
输出: 5->4->3->2->1->NULL
```
思路：
```

```
代码：
```python
class Solution:
    def reverseList(self, head: ListNode) -> ListNode:
        if not head or not head.next:
            return head
        nextNode = self.reverseList(head.next)
        head.next.next = head
        head.next = None
        return nextNode
```
