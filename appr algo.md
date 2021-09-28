```python

# 近似算法 approximation algorithm

# 创建列表，包含要覆盖的州
# 此处使用的是集合，其类似于列表，但不能包含重复元素
states_needed = set(['mt', 'wa', 'or', 'id', 'nv', 'ut', 'ca', 'az'])

# 创建可供选择的广播台清淡，此处使用的是散列表
stations = {}
stations['kone'] = set(['id', 'nv', 'ut'])
stations['ktwo'] = set(['wa', 'id,', 'mt'])
stations['kthree'] = set(['or', 'nv', 'ca'])
stations['kfour'] = set(['nv', 'ut'])
stations['kfive'] = set(['ca', 'az'])

# 使用一个集合来存储最终选择的广播台
final_stations = set()

# 算法
while states_needed:
	best_station = None
	states_covered = set()
	for station, states_for_station in stations.items():
		covered = states_needed & states_for_station  # 计算交集
		if len(covered) > len(states_covered):
			best_station = station
			states_covered = covered

	final_stations.add(best_station)
	states_needed -= states_covered
	print(best_station)


```
