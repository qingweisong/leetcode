问题：
```
给定一个二叉树，找出其最大深度。
二叉树的深度为根节点到最远叶子节点的最长路径上的节点数。
```
示例：
```
给定二叉树 [3,9,20,null,null,15,7]，
    3
   / \
  9  20
    /  \
   15   7
返回它的最大深度 3 。
```
说明：
```
叶子节点是指没有子节点的节点。
```
思路：
```
递归
1 root.left != None, 那么count_left += 1,继续遍历过程maxDepth(root.left),右侧同理。
2 注意    同一层中的输出有两个，分别计数当前节点为根节点时，左子树的深度和右子树的深度，哪个深，比较一下就好啦，记得迭代同时把当前层的深度不要漏掉
3 注意X2  （怎么停止）左右子树均为空，那么返回计数深度 1
```
代码：
```python
class Solution:
    def maxDepth(self, root: TreeNode) -> int:
        '''
        :type root:TreeNode
        :rtype: int
        '''
        # 上面未提及如果根节点直接为空， 无需遍历，返回0
        if root is None:
            return 0
        count1, count2 = 0, 0
        # 当前根节点的左子树是否为空
        if root.left != None:
            count1 += self.maxDepth(root.left) + 1
        # 当前根节点的右子树是否为空    
        if root.right != None:
            count2 += self.maxDepth(root.right) + 1
        # 当前节点为叶节点时，返回深度 1 
        if root.left == None and root.right == None:
            return 1
        return max(count1, count2)
```
