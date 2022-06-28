#data-science/tutorial/chapter2  
# 第二章 Python 介绍
所有编程语言的目的都是为了更方便地使用计算机来组织数据和处理数据，当然 Python 也不例外，瑞士计算机科学家尼古拉斯·沃斯(Niklaus Wirth)曾经说过，数据结构 + 算法 = 程序。其中，数据结构便是指如何组织数据，算法指的是如何处理数据。

## 1. 数据的来源
+ 内存。
存储在内存中的数据通常通过变量来访问，变量可以看成是存储值的容器，在 Python 中没有声明变量的命令，当为一个变量赋值时便创建了一个变量。
```python
a = 10
print(a)

b = 10.11
print(b)
```
+ 硬盘。
通过文件读入数据。
```python
with open('test.txt') as f:
    lines = f.readlines()
    for line in lines:
        print(line)
```
+ 终端输入。
通过终端读入数据。
```python
name = input("please input your name: ")
print(name)
```
+  网络。
通过网络获取数据。
```python
import requests

r = requests.get('https://www.baidu.com/robots.txt')
print(r.text)
```
## 2. 数据的类型
+ 数值类型
	+ 整数
	+ 浮点数
+ 字符类型
+ 布尔类型
+ 类型之间的转换
## 3. 数据的运算
+ 数值型
	+ `+，-，*，/`
+ 字符型
	+ `+，*` 以及一些对字符串进行处理的函数。
+ 布尔型
	+ and，or，not
## 4. 内置的数据结构
+ 列表
+ 集合
+ 字典
+ 元组
## 5. 数据处理流程的控制
+ 分支
+ 循环
+ 列表推导式
## 6. 代码模块化
+ 函数
+ 类
+ 模块


Python 作为一门易学易用以及功能强大的语言，在许多领域都得到了广泛的应用，特别是在数据科学和人工智能领域。下面我们就来简单介绍下 Python 这门语言。
## 1. 数据类型
### 1.1 对象
在 Python 中，一切皆对象，包括数字、字符、函数等。对象包含变量和作用于变量的函数，通过变量和函数，对象可以使复杂的事情变得简单和直接，在介绍其他之前，先来介绍变量和函数。
#### 1.1.1 变量
变量是存储值的容器，Python 中没有声明变量的命令，当为一个变量赋值时便创建了一个变量。

```python
>>> a = 3
>>> b = 4
>>> a + b
7
```

在 Python 中，要想改变一个变量的类型，只需要改变和变量关联的对象即可，这被称为动态类型。在下面的代码中，当把和变量 a 关联的对象由 3 改为 "three" 时，变量的类型也随之发生改变。

```python
>>> a = 3
>>> type(a)
<class 'int'>
>>> a = "three"
>>> type(a)
<class 'str'>
```

#### 1.1.2 函数
函数是一个代码块，只有在调用的时候才会被执行，可以通过参数往函数传递数据，函数可以将计算得到的数据作为结果返回。调用函数时，只需要在函数名后添加括号并传入相应的参数。在下面的代码中，定义了一个函数 `my_function()`，并调用，在调用时传入参数 "John"。

```python
>>> def my_function(name):
...     print("Hello " + name)
...
...
>>> my_function("John")
Hello John
```

### 1.2 数字类型
数据类型 `int` 和 `float` 分别代表整型和浮点型。为了查看指定对象的类型，可以使用 `type()` 方法。示例代码如下：

```python
>>> type(4)
<class 'int'>
>>> type(4.4)
<class 'float'>
```

如果想要将一个整型的数据转换为浮点型，可以在整型数据后面加上一个小数点或者使用 `float` 构造函数。示例代码如下：

```python
>>> type(4.)
<class 'float'>
>>> type(float(4))
<class 'float'>
```

同样地，使用 `int` 构造函数可以将一个浮点型数据转换为整型，如果浮点型数据的小数部门不为 0，在将其转换为整型数据时，小数部分会被丢弃。示例代码如下：

```python
>>> int(4.9)
4
```

#### 1.2.1 数学运算符
数字之间的运算需要数学运算符，例如：`+，-，*，/` 等。示例代码如下：

```python
>>> 3 + 14 # 加
17
>>> 14 - 3 #减
11
>>> 3 * 14 #乘
42
>>> 14 / 3 #除
4.666666666666667
>>> 14 % 3 #取余
2
>>> 14 // 3 #取整
4
>>> 14 ** 3 #乘方
2744
```

### 1.3 布尔型
布尔型变量的取值为 `True` 或 `False`，布尔操作符包括 `and`，`or` 和 `not`。示例代码如下：

```python
>>> 5 == 8
False
>>> 5 != 8
True
>>> 5 < 8
True
>>> 5 <= 8
True
>>> 5 < 8 < 10
True
>>> not True
False
>>> False and True
False
>>> False or True
True
```

为了验证一个对象是 `True` 或 `False`，可以使用 `bool` 构造函数。示例代码如下：

```python
>>> bool(2)
True
>>> bool(0)
False
>>> bool("abc")
True
>>> bool("")
False
>>> bool(None)
False
```

### 1.4 字符串
在 `Python` 中，字符串是用单引号(')或双引号(")括起来的一串字符，唯一的要求是字符串的起始引号和结束引号必须相同。我们可以使用 + 来拼接字符串，使用 * 来将一个字符串重复多次。示例代码如下：

```python
>>> "hello " + "world!"
'hello world!'
>>> "hello " * 3
'hello hello hello '
```

根据情况使用单引号或双引号可以避免对字符串中的字符进行转义，例如，当字符串中包含单引号时，这时候字符串的起始和结束引号使用双引号可以避免对字符串中的单引号进行转义；当字符串中包含双引号时，这时候字符串的起始和结束引号使用单引号可以避免对字符串中的双引号进行转义。当确实需要转义字符时，只需要在要转义的字符前面加上反斜杠 `\`。示例代码如下：

```python
>>> "Sorry, I'm late!" #不需要对单引号进行转义
"Sorry, I'm late!"
>>> 'The quote is "to be or not to be"' #不需要对双引号进行转义
'The quote is "to be or not to be"'
>>> print("It's easy to \"escape\" characters with a leading \\.") #对"和\转义
It's easy to "escape" characters with a leading \.
```

在字符串中混有变量时，可以使用 `f-strings` 来处理，只需要在字符串的前面添加 `f`，并且将变量放到花括号中。示例代码如下：

```python
>>> name = "Michael"
>>> age = 20
>>>
>>> f"Hello everyone, my name is {name}, I am {age} years old."
'Hello everyone, my name is Michael, I am 20 years old.'
```

由于字符串也是对象，所以它有一些自己的方法，如：`lower()`，`upper()`，`title()` 等，示例代码如下：

```python
>>> "HELLO WORLD!".lower() #将字符串中的每个字符小写
'hello world!'
>>> "hello world!".upper() #将字符串中的每个字符大写
'HELLO WORLD!'
>>> "hello world!".title() #将每个单词的首字母大写
'Hello World!'
```
## 2. 索引和切片
通过索引和切片可以访问序列中的特定元素。由于字符串是字符的序列，因此可以通过字符串来学习索引和切片的使用。
### 2.1 索引
在 Python 中，索引从 0 开始，也就是说序列中第一个元素对应的索引为 0，依次向后为 1，2，...。负数索引从 -1 开始，序列中最后一个元素对应的索引为 -1，依次向前为 -2，-3...。通过负数索引可以从后往前访问数据。具体概念如下图所示：

![[Pasted image 20220422133542.png]]

索引的语法如下：
`sequence[index]`
通过索引访问序列特定元素的示例代码如下：

```python
>>> lang = "PYTHON"
>>>
>>> lang[0]
'P'
>>> lang[2]
'T'
>>> lang[-1]
'N'
>>> lang[-3]
'H'
```

上面通过索引，一次只能访问一个元素，有时候我们需要一次访问多个元素，这时候便用到切片。
### 2.2 切片
如果一次想要访问多个元素，可以使用切片，语法如下：
`sequence[start:stop:step]`
在 Python 中，切片使用半开区间，也就是说最后得到的元素中包含索引 `start` 对应的元素不包含索引 `stop` 对应的元素。如果 `start` 缺失，则会从序列的第一个元素开始；如果 `stop` 缺失，则会到序列的最后一个元素结束，包含最后一个元素。`step` 决定着方向和步长，例如，`step` 为 2 表示从左到右每隔一个元素返回一个元素；`step` 为 -3 表示从右到左每隔两个元素返回一个元素。默认步长为 1。使用切片访问元素的示例代码如下：
```python
>>> lang = "PYTHON"
>>> lang[1:4]
'YTH'
>>> lang[:4]
'PYTH'
>>> lang[1:]
'YTHON'
>>> lang[-4:-1]
'THO'
>>> lang[:-1]
'PYTHO'
>>> lang[-4:]
'THON'
>>> lang[1:5:2]
'YH'
>>> lang[-1:-4:-1]
'NOH'
```
上面是单独使用索引或者切片访问序列元素的情况，另外，索引和切片还可以链在一起使用，例如，如果想访问 `lang` 最后三个元素中的第二个元素，则可以如下访问：
```python
>>> lang = "PYTHON"
>>> lang[-3:][1]
'O'
```
## 3. 数据结构
`Python` 提供了一些功能强大的数据结构，通过这些数据结构我们可以更加方便地处理对象的集合。这些数据结构包括列表、字典、元组和集合。
### 3.1 列表
列表能够保存多个不同数据类型的对象。可以通过如下的方式创建一个列表：
`[element1, element2, ...]`
下面是两个列表，一个列表的元素为 `Excel` 文件的名字，另一个列表中的元素为一些数字。
```python
>>> file_names = ["a.xlsx", "b.xlsx", "c.xlsx"]
>>> file_names
['a.xlsx', 'b.xlsx', 'c.xlsx']
>>> numbers = [1, 2, 3]
>>> numbers
[1, 2, 3]
```
像字符串一样，列表也支持使用`+`号进行拼接，示例代码如下：
```python
>>> file_names = ["a.xlsx", "b.xlsx", "c.xlsx"]
>>> numbers = [1, 2, 3]
>>> file_names + numbers
['a.xlsx', 'b.xlsx', 'c.xlsx', 1, 2, 3]
```
上面的代码也说明了列表可以保存不同类型的对象。由于列表也是对象，因此列表也可以将其他列表作为自己的元素，这样的列表称为嵌套列表，示例代码如下：
```python
>>> nested_list = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
>>> nested_list
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```
列表 `nested_list` 中的每个元素为一个列表。嵌套列表也可以通过索引或切片进行访问，示例代码如下：
```python
>>> nested_list = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
>>> nested_list[1][1]
5
>>> nested_list[1][1:]
[5, 6]
>>> nested_list[1]
[4, 5, 6]
```
可以通过 `append()` 和 `insert()` 方法往列表中添加元素，示例代码如下：
```python
>>> users = ["Linda", "Brian"]
>>> users.append("Jennifer")
>>> users
['Linda', 'Brian', 'Jennifer']
>>> users.insert(0, "Kim")
>>> users
['Kim', 'Linda', 'Brian', 'Jennifer']
```
在使用 `insert()` 方法时，第一个参数为插入的位置，第二个参数为要插入的元素。从列表中删除一个元素可以使用 `pop()` 方法或者 `del` 语句，示例代码如下：
```python
>>> users = ['Kim', 'Linda', 'Brian', 'Jennifer']
>>> users
['Kim', 'Linda', 'Brian', 'Jennifer']
>>> users.pop()
'Jennifer'
>>> users
['Kim', 'Linda', 'Brian']
>>> users.pop(1)
'Linda'
>>> users
['Kim', 'Brian']
>>> del users[1]
>>> users
['Kim']
```
`pop()` 方法默认删除并返回列表中的最后一个元素，也可以参数指定要删除那个元素；`del` 语句删除指定的元素。另外还有一些有用的针对列表的操作，示例代码如下：
```python
>>> # 使用 len() 方法获取列表的长度
>>> users = ['Kim', 'Linda', 'Brian', 'Jennifer']
>>> len(users)
4
```

```python
>>> # 判断列表中是否包含某个元素
>>> users = ['Kim', 'Linda', 'Brian', 'Jennifer']
>>> 'Linda' in users
True
```

```python
>>> # 对列表进行排序
>>> users = ['Kim', 'Linda', 'Brian', 'Jennifer']
>>> sorted(users) # 返回一个新的排序后的列表
['Brian', 'Jennifer', 'Kim', 'Linda']
>>> users # 原列表不发生改变
['Kim', 'Linda', 'Brian', 'Jennifer']
>>> users.sort() # 对原列表进行排序
>>> users
['Brian', 'Jennifer', 'Kim', 'Linda']
```
### 3.2 字典
字典将键映射到值，是键值对的集合。最简单的创建字典的方法如下：
`{key1: value1, key2: value2, ...}`
可以通过键访问字典中的元素，和列表的索引一样，使用的也是方括号`[]`，示例代码如下：
```python
>>> car_dict = {
... "brand": "Ford",
... "model": "Mustang",
... "year": 1964
... }
>>> car_dict["brand"]
'Ford'
```
除了访问字典中的元素之外，还可以修改字典中的值以及向字典中添加新的键值对，示例代码如下：
```python
>>> car_dict = {
... "brand": "Ford",
... "model": "Mustang",
... "year": 1964
... }
>>> car_dict
{'brand': 'Ford', 'model': 'Mustang', 'year': 1964}
>>> car_dict["year"] = 1968 # 修改字典中的值
>>> car_dict
{'brand': 'Ford', 'model': 'Mustang', 'year': 1968}
```

```python
>>> car_dict = {
... "brand": "Ford",
... "model": "Mustang",
... "year": 1964
... }
>>> car_dict
{'brand': 'Ford', 'model': 'Mustang', 'year': 1964}
>>> car_dict["color"] = "red" # 向字典中添加新的元素
>>> car_dict
{'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'red'}

```
合并两个以上字典的最简单方法是取出字典中的元素并把它们放到一个新的字典中，取出字典中元素的方法是在字典前面使用`**`，如果第二个字典中的键和第一个字典有重复，则第一个字典中相应的键对应的值会被覆盖。示例代码如下：
```python
>>> car_dict = {
... "brand": "Ford",
... "model": "Mustang",
... "year": 1964
... }
>>> {**car_dict, **{"color": "red", "type": "SUV"}}
{'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'red', 'type': 'SUV'}
```
Python 3.9 引入了管道符号，专用于字典的合并操作，使用管道符号，可以将上面的合并操作简化成如下形式：
```python
>>> car_dict = {
... "brand": "Ford",
... "model": "Mustang",
... "year": 1964
... }
>>> car_dict | {"color": "red", "type": "SUV"}
{'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'red', 'type': 'SUV'}
```
在使用方括号 `[]` 访问字典中的元素时，当键不存在时，会报错；而使用 `get` 方法，当键不存在时，允许返回一个默认值，示例代码如下：
```python
>>> car_dict = {
... "brand": "Ford",
... "model": "Mustang",
... "year": 1964
... }
>>> car_dict["color"]
Traceback (most recent call last):
  File "<input>", line 1, in <module>
    car_dict["color"]
KeyError: 'color'
>>> car_dict.get("color", "white")
'white'
```
介绍完字典之后，接下来介绍元组，元组和列表类似，不过有一个很大的不同，我们接下来介绍。
### 3.3 元组
元组和列表类似，所不同的是元组不可改变，一旦创建，元组中的元素是不可改变的。在某些情况下，元组和列表可以交换着使用，但是对于在整个程序执行过程中都不改变的集合来说，元组是最佳选择。在定义元组时，元素之间使用逗号分隔。创建语法如下：
`my_tuple = elem1, elem2, ...`
通常情况下会用括号将元素括起来，这样更容易阅读。例如：
```python
>>> fruit_tuple = ("apple", "pear", "banana")
>>> fruit_tuple
('apple', 'pear', 'banana')
```
我们可以使用和访问列表元素同样的方法来访问元组中的元素，不同的是不能改变元组中的元素。示例代码如下：
```python
>>> fruit_tuple = ("apple", "pear", "banana")
>>> fruit_tuple
('apple', 'pear', 'banana')
>>> fruit_tuple[2]
'banana'
>>> fruit_tuple[0:2]
('apple', 'pear')
```
拼接两个元组会生成一个新的元组，示例代码如下：
```python
>>> fruit_tuple = ("apple", "pear", "banana")
>>> fruit_tuple
('apple', 'pear', 'banana')
>>> fruit_tuple_add = ("orange", "grape")
>>> fruit_tuple_add
('orange', 'grape')
>>> fruit_tuple + fruit_tuple_add
('apple', 'pear', 'banana', 'orange', 'grape')
```

### 3.4 集合
集合是不包含重复元素的集合，可以用来做一些集合运算或者去除列表、元组中重复的元素。创建语法如下：
`my_set = {elem1, elem2, ...}`
用花括号括起来以逗号分隔的元素。为了去除元组中的重复元素，可以使用集合的构造函数，示例代码如下：
```python
>>> my_tuple = ("apple", "pear", "orange", "apple", "orange")
>>> my_tuple
('apple', 'pear', 'orange', 'apple', 'orange')
>>> set(my_tuple)
{'pear', 'apple', 'orange'}
```
另外，可以进行一些集合的运算，例如：交集、并集等。示例代码如下：
```python
>>> my_set1 = {"apple", "pear", "orange"}
>>> my_set2 = {"apple", "grape"}
>>> my_set1.union(my_set2)
{'apple', 'grape', 'pear', 'orange'}
>>> my_set1.intersection(my_set2)
{'apple'}
```
## 4. 控制流
在 `Python` 中，控制流语句包括 `if` 语句，`for` 和 `while` 循环。`if` 语句可以根据条件来控制某块代码是否执行，`for` 和 `while` 循环会重复执行某块代码。
### 4.1 代码块和pass语句
代码块定义了一块具有特殊用途的代码。例如，可以使用代码块定义一块需要重复执行的代码或者定义函数的函数体。在 `Python 中`，使用缩进的方式定义代码块，不像其他语言使用花括号，默认使用四个空格进行缩进，在输入四个空格时，通常使用 `Tab` 键，像 `Jupyter Notebooks` 和 `VS Code` 都会自动地将 `Tab` 键转换为四个空格。下面通过 `if` 语句说明如何定义代码块。
```python
if condition:
	pass # Do nothing
```
代码块前面的一行代码通常以 `:` 结尾，当代码不再进行缩进时，便到达了代码块的结尾。如果你想定义一个什么都不做的代码块，可以使用 `pass` 语句。
### 4.2 if语句和条件表达式
在程序设计中，有时候需要根据某些条件是否成立来决定是否执行某段代码，这时候便用到了 `if` 语句，`if` 语句的语法为 `if...elif...else` 。

### 4.3 for和while循环
在 Python 中，如果需要重复执行某个代码块多次，可以使用 `for` 循环或者 `while` 循环。例如
```python
>>> for i in range(6):
...     print(i)
...
...
0
1
2
3
4
5
```


### 4.4 列表、字典和集合推导式

## 5. 组织代码
### 5.1 函数
函数的使用可以达到代码复用的目的，避免了同一块代码在多个地方出现，使得代码也更易于维护，如果需要改变函数的实现，只需要改变函数的定义即可，使用函数的地方不需要改变，大大降低了产生错误的概率。
#### 5.1.1 函数的定义
函数的定义以关键字 `def` 开头，语法如下：
```python
def function_name(required_argument, optional_argument=default_value,...):
	statetment
	
	return value1, value2,...
```

### 5.2 模块和import语句
### 5.3 类
## 6. 代码风格指南