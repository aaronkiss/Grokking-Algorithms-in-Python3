Binary search

```python

lis = input('Please input an array: ')
nums = [int(n) for n in lis.split()]
# nums.sort()
print(nums)


def search(nums: [int], target: int) -> int:
	low, high = 0, len(nums) - 1
	while low <= high:
		mid = (low + high) // 2 + low
		num = nums[mid]
		if num == target:
			return mid
		elif num >= target:
			high = mid - 1
		else:
			low = mid + 1
	return -1


print(search(nums, 3))


```
