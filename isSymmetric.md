问题：
```
给定一个二叉树，检查它是否是镜像对称的。
例如，二叉树 [1,2,2,3,4,4,3] 是对称的。
    1
   / \
  2   2
 / \ / \
3  4 4  3
但是下面这个 [1,2,2,null,3,null,3] 则不是镜像对称的:
    1
   / \
  2   2
   \   \
   3    3
```
思路：
```
1）是否为完整二叉树 2）树的左节点是否与树的右节点相等
```
代码：
```python
class Solution:
    def isSymmetric(self, root: TreeNode) -> bool:
        #空树也是对称的
        if root == None:
            return True
            
        def help(left, right):
            
            if left == None and right == None:
                return True
            if left == None or right == None:
                return False
            if left.val != right.val:
                return False
            return help(left.left, right.right) and help(left.right, right.left)
        #手动调用进入函数
        return help(root, root)
```
