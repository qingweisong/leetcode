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
函数中的函数需手动调用
递归算法 调用自身
1.传入root.left(null)    进入if return
2.res.append(1)
3.传入root.right(2)  不进入if  传入root.left(3)  传入3.left  进入if return res.append(3)  传入3.right  进入if  returrn   
4.res.append(2)
5.传入2.right(null) return
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
        #
        helper(root)
        return res
```
