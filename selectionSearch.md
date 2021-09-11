Selection search

```python

nums = input('请输入一个数组：')
nums = [int(n) for n in nums.split()]


# print(nums)


def findSmallest(nums):
	smallest = nums[0]  # 存储最小值
	smallest_index = 0  # 存储最小值索引
	for i in range(1, len(nums)):  # 在剩余的元素中遍历
		if nums[i] < smallest:  # 如果该元素比之前的最小值还小
			smallest = nums[i]  # 就用该元素替代之前的最小值
			smallest_index = i  # 就用该元素的索引替代之前的最小值索引
	return smallest_index  # 返回最小值索引


def selectionSort(nums):
	newArr = []  # 创建空的新数组
	for i in range(len(nums)):  # 遍历原始数组各个元素
		smallest = findSmallest(nums)  # 将上一个函数返回的最小值赋予变量最小值
		newArr.append(nums.pop(smallest))  # 将最小值从原始数组剔除并存入新数组
	return newArr


print(selectionSort(nums))


```
