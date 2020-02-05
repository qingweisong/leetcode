问题：
```
给你一个数组 arr ，请你将每个元素用它右边最大的元素替换，如果是最后一个元素，用 -1 替换。
完成所有替换操作后，请你返回这个数组。
```
示例：
```
输入：arr = [17,18,5,4,6,1]
输出：[18,6,6,6,1,-1]
```
提示：
```
1 <= arr.length <= 10^4
1 <= arr[i] <= 10^5
```
思路：
```
数组 arr 中的每个元素 arr[i]替换成 arr[i + 1], arr[i + 2], ..., arr[n - 1] 中的最大值：
逆序地遍历整个数组，同时维护从数组右端到当前位置所有元素的最大值。
设 ans[i] = max(arr[i + 1], arr[i + 2], ..., arr[n - 1])，那么在进行逆序遍历时，ans[i] = max(ans[i + 1], arr[i + 1])
```
代码：
```python
class Solution:
    def replaceElements(self, arr: List[int]) -> List[int]:
        n = len(arr)
        ans = [0] * (n - 1) + [-1]
        #从倒数第二个值逆序遍历
        for i in range(n - 2, -1, -1):
            ans[i] = max(ans[i + 1], arr[i + 1])
        return ans
```
