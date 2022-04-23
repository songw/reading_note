#python/ds/list/methods
# 列表的方法
---
## append()
### 定义和用法
`append()` 方法在列表的末尾添加一个元素。
### 语法
`list.append(elem)`

+ elem 代表任意类型的元素。
### 示例
```python
>>> fruit = ["apple", "banana"]
>>> fruit
['apple', 'banana']
>>> fruit.append("cherry")
>>> fruit
['apple', 'banana', 'cherry']
```

---
## clear（）
### 定义和用法
`clear()` 方法从列表中删除所有的元素。
### 语法
`list.clear()`
### 示例
```python
>>> fruit = ["apple", "banana", "cherry"]
>>> fruit
['apple', 'banana', 'cherry']
>>> fruit.clear()
>>> fruit
[]
```
---
## copy()
### 定义和用法
`copy()` 方法返回列表的拷贝。
### 语法
`list.copy()`
### 示例
```python
>>> fruit = ["apple", "banana", "cherry"]
>>> fruit
['apple', 'banana', 'cherry']
>>> fruit_copy = fruit.copy()
>>> fruit_copy
['apple', 'banana', 'cherry']
```
---
## count()
### 定义和用法
`count()` 返回列表中某个值出现的次数。
### 语法
`list.count(value)`
+ value 表示要查找的值。
### 示例
```python
>>> fruit = ["apple", "banana", "cherry", "apple", "apple"]
>>> fruit.count("apple")
3
```
---
## extend()
### 定义和用法
`extend()` 方法将任何可迭代对象中的元素添加到当前列表的末尾。
### 语法
`list.extend(iterable)`
+ iterable 表示任意可迭代对象。
### 示例
#### 示例1
```python
>>> fruit = ["apple", "banana", "cherry"]
>>> fruit
['apple', 'banana', 'cherry']
>>> fruit_add = ["pear", "orange"]
>>> fruit.extend(fruit_add)
>>> fruit
['apple', 'banana', 'cherry', 'pear', 'orange']
```
#### 示例2
```python
>>> fruit = ["apple", "banana", "cherry"]
>>> fruit
['apple', 'banana', 'cherry']
>>> numbers = (1, 2, 3)
>>> numbers
(1, 2, 3)
>>> fruit.extend(numbers)
>>> fruit
['apple', 'banana', 'cherry', 1, 2, 3]
```
---
## index()
### 定义和用法
`index()` 方法返回列表中某个值第一次出现的位置。
### 语法
`list.index(elem)`
+ elem 表示要查找的元素。
### 示例
```python
>>> fruit = ["apple", "banana", "cherry", "apple", "apple"]
>>> fruit
['apple', 'banana', 'cherry', 'apple', 'apple']
>>> fruit.index("apple")
0
```
---
## insert()
### 定义和用法
`insert()` 方法在指定位置添加一个值。
### 语法
`list.insert(pos, elem)`
+ pos 表示要插入的位置。
+ elem 表示要插入的元素。
### 示例
```python
>>> fruit = ["apple", "banana", "cherry"]
>>> fruit
['apple', 'banana', 'cherry']
>>> fruit.insert(1, "orange")
>>> fruit
['apple', 'orange', 'banana', 'cherry']
```
---
## pop()
### 定义和用法
`pop()` 方法删除指定位置的元素。
### 语法
`list.pop(pos)`
+ pos 参数是可选的，用来指定要删除元素的位置，默认为 -1，返回列表的最后一个元素。
### 示例
```python
>>> fruit = ["apple", "banana", "cherry"]
>>> fruit
['apple', 'banana', 'cherry']
>>> fruit.pop()
'cherry'
>>> fruit
['apple', 'banana']
>>> fruit.pop(1)
'banana'
>>> fruit
['apple']
```
---
## remove()
### 定义和用法
`remove()` 方法删除具有指定值的第一次出现的元素。
### 语法
`list.remove(elem)`
+ elem 表示要删除的元素。
### 示例
```python
>>> fruit = ["apple", "banana", "cherry", "apple", "apple"]
>>> fruit
['apple', 'banana', 'cherry', 'apple', 'apple']
>>> fruit.remove("apple")
>>> fruit
['banana', 'cherry', 'apple', 'apple']
```
---
## reverse()
### 定义和用法
`reverse()` 方法翻转整个列表。
### 语法
`list.reverse()`
### 示例
```python
>>> fruit = ["apple", "banana", "cherry"]
>>> fruit
['apple', 'banana', 'cherry']
>>> fruit.reverse()
>>> fruit
['cherry', 'banana', 'apple']
```
---
## sort()
### 定义和用法
`sort()` 方法默认按照升序对列表中的元素进行排序，另外可以通过自定义的函数指定排序的条件。
### 语法
`list.sort(reverse=True|False, key=myFunc)`
+ `reverse=True` 表示按照降序排序，默认 `reverse=False`，表示按照升序排序。
+ `key=myFunc` 表示通过自定义的函数指定排序的条件。
### 示例
#### 示例1
```python
>>> fruit = ["apple", "banana", "cherry"]
>>> fruit
['apple', 'banana', 'cherry']
>>> fruit.sort(reverse=True)
>>> fruit
['cherry', 'banana', 'apple']
```
#### 示例2
```python
>>> def myFunc(e):
...     return len(e)
...
>>> fruit = ["apple", "pear", "banana"]
>>> fruit
['apple', 'pear', 'banana']
>>> fruit.sort(key=myFunc)
>>> fruit
['pear', 'apple', 'banana']
```