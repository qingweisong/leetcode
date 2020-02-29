问题：
```
给定一个二叉树，返回它的中序 遍历。
```
示例：
```
输入: [1,null,2,3]
   1
    \
     2
    /
   3

输出: [1,3,2]
```
思路：
```

```
代码：
```python
class Solution:
    def inorderTraversal(self, root: TreeNode) -> List[int]:
        res = []
        def helper(root):
            if not root:
                return 
            helper(root.left)
            res.append(root.val)
            helper(root.right)
        helper(root)
        return res
```
