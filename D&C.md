```python

# divide and conquer 分而治之

# 循环求和的方法
def sum(arr):
	total = 0
	for x in arr:
		total += x
	return total

print(sum([1, 3, 5]))

# 递归函数的方法 即课后4.1
def sum(arr):
	if len(arr) == 0:
		return 0
	else:
		return arr[0] + sum(arr[1:])

print(sum([2, 4, 6]))

# 小节课后练习
# 4.2
def count(i):
	if len(i) == 0:
		return 0
	else:
		return 1 + count(i[1:])

print(count([1, 3, 5, 7, 9]))

# 4.3
# 网上的一种思路
def max(arr):
	if len(arr) == 1:
		return arr[0]
	else:
		m = max(arr[:len(arr) - 1])
		if m > max(arr[:len(arr) - 1]):
			return m
		else:
			return arr[len(arr) - 1]

print(max([1, 3, 5, 7, 9]))

# 网上的另一种思路
def find_max(arr):
	tmp = arr.pop(0)
	if len(arr) == 0:
		return tmp
	max = find_max(arr)
	if max > tmp:
		return max
	else:
		return tmp

print(find_max([1, 3, 5, 7, 9]))
# 两个思路都需要用到新的变量

```
