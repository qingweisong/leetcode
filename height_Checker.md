问题：
```
学校在拍年度纪念照时，一般要求学生按照 非递减 的高度顺序排列。
请你返回能让所有学生以 非递减 高度排列的最小必要移动人数。
```
示例：
```
输入：heights = [1,1,4,2,1,3]
输出：3
```
提示：
```
1 <= heights.length <= 100
1 <= heights[i] <= 100
```
思路：
```
1 对表示学生身高的数组排序得到一个排序后的新数组
2 对比排序后数组和原数组，记录下标值相同但元素值不同的下标个数，即为拍错位置的学生个数。
```
代码：
```python
class Solution:
    def heightChecker(self, heights: List[int]) -> int:
        res = 0

        sorted_stu = sorted(heights)
        n = len(heights)

        for i in range(n):
            if heights[i] != sorted_stu[i]:
                res += 1
        return res
```
