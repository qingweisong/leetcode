问题：
```
给你个整数数组 arr，其中每个元素都不相同。
请你找到所有具有最小绝对差的元素对，并且按升序的顺序返回。
```
示例：
```
输入：arr = [4,2,1,3]
输出：[[1,2],[2,3],[3,4]]

输入：arr = [1,3,6,10,15]
输出：[[1,3]]

输入：arr = [3,8,-10,23,19,-4,-14,27]
输出：[[-14,-10],[19,23],[23,27]]
```
提示：
```
2 <= arr.length <= 10^5
-10^6 <= arr[i] <= 10^6
```
思路：
```
先排序，再逐一遍历数组元素。
```
代码：
```python
class Solution:
    def minimumAbsDifference(self, arr: List[int]) -> List[List[int]]:
        arr.sort()
        if len(arr)<3:
            return [arr]
        mindiff=arr[1]-arr[0]
        res=[[arr[0],arr[1]]]
        for i in range(2,len(arr)):
            curdiff=arr[i]-arr[i-1]
            if curdiff<mindiff:
                res=[[arr[i-1],arr[i]]]
                mindiff=curdiff
            elif curdiff==mindiff:
                res.append([arr[i-1],arr[i]])
        return res
```
