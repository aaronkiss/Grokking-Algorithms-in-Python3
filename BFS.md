```python

# BFS 广度优先搜索
from collections import deque

graph = {}
graph["you"] = ['Alice', 'Bob', 'Claire']
graph["Bob"] = ['Anu', 'Peggy']
graph['Alice'] = ['Peggy']
graph["Claire"] = ['Thom', 'Jonny']
graph["Anu"] = []
graph["Peggy"] = []
graph["Thom"] = []
graph["Jonny"] = []

def search(name):
	search_queue = deque()  # 创建队列
	search_queue += graph[name]  # 将邻居都加入队列
	searched = []  # 用于记录已检查过的人
	while search_queue:  # 只要队列不为空
		person = search_queue.popleft()  # 就取出其中的一个人
		if person_is_seller(person):  # 检查此人是否为芒果商
			print(person + ' is a mango seller!')  # 如果是芒果商，就打印他
			return True
		else:
			search_queue += graph[person]  # 如果不是，就将此人的朋友加入搜索队列
			searched.append(person)  # 将此人标记为检查过的人
	return False  # 若运行到此处，说明队列里没有芒果商

def person_is_seller(name):
	return name[-1] == 'm'  # 如果名字是以 m 结尾的就判断为芒果商

search("you")


```
