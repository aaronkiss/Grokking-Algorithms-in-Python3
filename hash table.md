```python

# 散列表 在 python中的名字叫"字典"
book = dict()

book['apple'] = 0.67
book['milk'] = 1.49
book['avocado'] = 1.49

print(book)
print(book['avocado'])

phone_book = {}  # 是另一种创建散列表（字典）的简便方式
phone_book['Jenny'] = 13820974409
phone_book['Lucy'] = 13922094486
phone_book['Sally'] = 13693533120
print(phone_book)
print(phone_book['Jenny'])

# 用散列表（字典）来判断输入的名字是否已经投票
voted = {}

def check_voter(name):
	if voted.get(name):
		print('kick them out!')
	else:
		voted[name] = True
		print('let them vote')

name = input("Please enter voter's name: ")
print(check_voter(name))


```
