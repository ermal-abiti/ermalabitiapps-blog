---
path: python-selectionsort
date: 2020-07-21T12:25:21.666Z
title: Selection-Sort Algorithm In Python
---
```python
def selectionSort(unsortedArray):
	array = []
	
	for i in range(len(unsortedArray)):
		array.append(unsortedArray[i])
	
	for i in range(len(array)):
		minIndex = i
		for j in range(i, len(array)):
			if (array[j] < array[minIndex]):
				minIndex = j
		
		temp = array[i]
		array[i] = array[minIndex]
		array[minIndex] = temp
	
	return array
```