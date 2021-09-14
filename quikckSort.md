```python

# 快速排序

def quickSort(arr):
	if len(arr) < 2:  # 基线条件
		return arr
	else:
		pivod = arr[0]  # 设定基准值
		less = [i for i in arr[1:] if i <= pivod]  # 比基准值小的元素
		greater = [i for i in arr[1:] if i > pivod]  # 比基准值大的元素
		return quickSort(less) + [pivod] + quickSort(greater)  # 拼接数组

print(quickSort([10, 5, 2, 3]))


```
