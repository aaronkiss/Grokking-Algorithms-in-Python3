```python

# 迪科斯特拉算法
import collections

graph = {}
graph['you'] = ['alice', 'bob', 'claire']

# 创建加权图
graph['start'] = {}
graph['start']['a'] = 6  # start -> a 的权重
graph['start']['b'] = 2  # start -> b 的权重
print(graph['start'].keys())  # 获得start的所有邻居
print(graph['start']['a'])  # 获得 start -> a 的权重
print(graph['start']['b'])  # 获得 start -> b 的权重
graph['a'] = {}
graph['a']['fin'] = 1
graph['b'] = {}
graph['b']['a'] = 3
graph['b']['fin'] = 5
graph['fin'] = {}

# 这是储存开销的散列表
infinity = float('inf')  # 对于未知的开销，将其设置为 ：无穷大
costs = {}
costs['a'] = 6
costs['b'] = 2
costs['fin'] = infinity

# 这是储存父节点的散列表
parents = {}
parents['a'] = 'start'
parents['b'] = 'start'
parents['fin'] = None

# 需要创建一个数组用于记录处理过的节点，以避免重复处理
processed = []

print('The best path is:')
print('start \n  ' + chr(0x2193))

path_node = collections.deque()  # 建立空双向列表以储存运算后的路径节点
# 算法实现
def find_lowest_cost_node(costs):
	lowest_cost = float('inf')
	lowest_cost_node = None
	for node in costs:  # 遍历所有节点
		cost = costs[node]
		if cost < lowest_cost and node not in processed:  # 如果当前节点的开销更低且未被处理
			lowest_cost = cost  # 就将其视为开销最低的节点
			lowest_cost_node = node
	return lowest_cost_node

node = find_lowest_cost_node(costs)  # 在未处理的节点中找出开销最小的节点
while node is not None:  # while 循环将遍历所有节点
	cost = costs[node]
	neighbors = graph[node]
	for n in neighbors.keys():  # 遍历当前节点的所有邻居
		new_cost = cost + neighbors[n]  # 从父节点到当前节点的开销 + 从当前节点到邻居的开销
		if costs[n] > new_cost:  # 如果经当前节点前往该邻居更近
			costs[n] = new_cost  # 就更新该邻居的开销
			parents[n] = node  # 同时把该邻居的父节点设置为当前节点
	path_node.append(parents[n])
	processed.append(node)  # 将当前节点标记为处理过的节点
	node = find_lowest_cost_node(costs)  # 找出接下来要处理的节点，并循环

# 解决了输出结果出现重复的问题，并优化了输出效果
path_node.appendleft('start')
path_node.append('end')
path = []
for i in path_node:
	if not i in path:
		path.append(i)

for n in path:
	if n != 'end':
		print(n, end = ' ' + chr(0x2192) + ' ')
	else:
		print('end')


```

### But there is one problum is that two times printed the same node in resurlt.
How fix it smartly... 
### Update on 9-28-21
I get some point from web, and fix the output effect.
