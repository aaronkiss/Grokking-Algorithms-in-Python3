```python

# 递归函数应包含递归条件和基线条件
# 递归条件让函数调用自己
# 基线条件避免递归函数无限循环

def countdown(i):
	print(i)
	if i <= 1:  # 基线条件
		return
	else:  # 递归条件
		countdown(i - 1)


countdown(100)
print('\n')


# 调用栈
# factorial 阶乘 5! = 5*4*3*2*1
def fact(x):
	if x == 1:
		return 1
	else:
		return x * fact(x - 1)


print(fact(5))

```
