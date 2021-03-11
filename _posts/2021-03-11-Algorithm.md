---
layout: post
title: Algorithm
feature-img: "assets/img/feature-img/circuit.jpeg"
thumbnail: "assets/img/thumbnails/feature-img/circuit.jpeg"
tags: [Algorithm]
---


알고리즘 리뷰:

1. Bubble Sort
2. selection sort


## 정의

1-1. Bubble sort 란?
- 두 인접한 데이터를 비교해서, 앞에 있는 데이터가 뒤에 있는 데이터보다 크면 자리를 바꾸는 정렬 알고리즘

### Python

```python
	def bubblesort(data):
		for index in range(len(data)-1):
			swap=False
			for index2 in range(len(data)- index-1): //할 때마다 가장 높은 값이 맨뒤로 하나씩 놓이기 때문에 끝까지 검색할 필요가 없음
				if data[index2]>data[index2+1]:
					data[index2], data[index2+1]=data[index2+1], data[index2]
					swqp=True
			if swap==False:
				break
		return data
	
	import random
	
	data_list = random.sample(range(100), 50)
print (bubblesort(data_list))

```
1-2. 알고리즘 분석
- data 길이 n, 그 안에서 n번 => 반복문이 두 개 => n*n
- O(n^2)
- 최악의 경우 n*(n-1)/2
- 완전 정렬되어있는 상태면 최선은 O(n) (한번만 돌면 되니까)

## 정의

2-1. Selection sort란?
- 다음과 같은 순서를 반복하며 정렬하는 알고리즘
  (1) 주어진 데이터 중, 최소값을 찾음
  (2) 해당 최소값을 데이터 맨 앞에 위치한 값과 교체함
  맨 앞의 위치를 뺀 나머지 데이터를 동일한 방법으로 반복함
  
### Python
```python
def selection_sort(data):
	for stand in range(len(data)-1):
		lowest=stand
		for index in range(stand+1, len(data)):
			if data[lowest]>data[index]:
				lowest=index
		data[lowest],data[stand]=data[stand],data[lowest]//data[stand]가 기준, 가장 작은 값과 위치 바꾸면 됨
	return data
	
import random
data_list=random.sample(range(100),10)
selection_sort(data_list)![image](https://user-images.githubusercontent.com/66209090/110746468-34e85c00-8280-11eb-9496-e463ad6075ba.png)


```
