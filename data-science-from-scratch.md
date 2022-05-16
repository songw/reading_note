#data-science/tutorial 
# 前言
Python 具有的如下几个特征使得它特别适合用来学习数据科学。
+ Python 是免费的。
+ 使用 Python 进行编程是相对容易的。
+ 有许多有用的数据科学相关的库。
# 第一章 介绍
## 1. 数据无处不在
我们生活在一个被数据淹没的世界。网站记录每个用户的每次点击；你的智能手机每时每刻都在记录着你的位置和移动速度；智能汽车收集司机的驾驶习惯；智能家居收集主人的生活习惯；聪明的营销人员收集客户的购买习惯；

## 2. 什么是数据科学？
[Data Scientist: The Sexiest Job of the 21st Century](https://hbr.org/2012/10/data-scientist-the-sexiest-job-of-the-21st-century)
## 3. 数据科学的工作内容

# 第二章 Python 介绍
Python 作为一门易学易用以及功能强大的语言，在许多领域都得到了广泛的应用，特别是在数据科学和人工智能领域。下面我们就来简单介绍下 Python 这门语言。
## 1. 数据类型
### 1.1 对象
在 Python 中，一切皆对象，包括数字、字符、函数等。对象包含变量和作用于变量的函数，通过变量和函数，对象可以使复杂的事情变得简单和直接，在介绍其他之前，先来介绍下变量和函数。
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
### 4.4 列表、字典和集合推导式
## 5. 组织代码
### 5.1 函数
### 5.2 模块和import语句
### 5.3 类
## 6. 代码风格指南
# 第三章 数据可视化
数据可视化有两个主要用途：
+ 探索数据。
+ 解释数据。

## 1. matplotlib
数据可视化工具有很多种，我们将要介绍的为 `matplotlib`。如果你已经安装了 `Python` 和 `PIP`，那么安装 `matplotlib` 将非常简单，只需要在终端中执行如下命令：
`pip install matplotlib`
`matplotlib` 安装完成之后，便可以使用 `matplotlib` 做图了。由于 `matplotlib` 的大多数功能位于 `pyplot` 子模块中，所以一般导入的是 `pyplot` 子模块。导入的代码为：
`from matplotlib import pyplot as plt`
在导入的时候一般会给 `pyplot` 模块起一个别名 `plt`，这样通过 `plt` 便可以引用 `pyplot` 包。介绍完 `matplotlib` 之后，下面介绍几种常见图形的绘制。
## 2. 折线图
折线图是一个由点和线组成的统计图表，常用来表示数值随连续时间间隔或有序类别的变化。在折线图中，`x` 轴通常用作连续时间间隔或有序类别（比如阶段1，阶段2，阶段3）。`y` 轴用于量化的数据，如果为负值则绘制于 `y` 轴下方。连线用于连接两个相邻的数据点。

折线图用于分析事物随时间或有序类别而变化的趋势。如果有多组数据，则用于分析多组数据随时间变化或有序类别的相互作用和影响。折线的方向表示正/负变化。折线的斜率表示变化的程度。

下面通过具体的示例介绍折线图的绘制，代码如下：

```python
from matplotlib import pyplot as plt

dev_x = [25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35]
dev_y = [38496, 42000, 46752, 49320, 53200, 56000, 62316, 64928, 67317, 68748, 73752]

plt.plot(dev_x, dev_y)
plt.show()
```

上述代码的第一行从 `matplotlib` 导入 `pyplot` 并起别名 `plt`。`dev_x、dev_y` 为两个列表，分别包含 11 个数据，接下来调用 `plot` 函数便可以进行作图，`plot` 函数的参数为两组数据，调用 `plot` 函数之后，还需要调用 `show` 函数，否则不会显示图形。上述代码得到的图形如下所示：

![[Pasted image 20220427113043.png]]

上面只是作了一条折线图，横坐标、纵坐标所表示的含义以及整个图形的标题并没有进行说明，下面通过调用一些方法来添加上述信息，代码如下：

```python
from matplotlib import pyplot as plt

dev_x = [25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35]
dev_y = [38496, 42000, 46752, 49320, 53200, 56000, 62316, 64928, 67317, 68748, 73752]

plt.plot(dev_x, dev_y)

plt.xlabel("年龄")
plt.ylabel("年薪")
plt.title("年龄和薪水的关系")

plt.show()
```

上述代码通过 `xlabel()` 函数添加横坐标代表的含义，通过 `ylabel()` 函数添加纵坐标代表的含义，通过 `title()` 函数添加图形的标题。添加上述信息之后的图形如图所示：

![[Pasted image 20220427113134.png]]

同一个图形中可以包含多条折线，下面就来添加其他的折线，代码如下：

```python
from matplotlib import pyplot as plt

dev_x = [25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35]
dev_y = [38496, 42000, 46752, 49320, 53200, 56000, 62316, 64928, 67317, 68748, 73752]
plt.plot(dev_x, dev_y)

py_dev_x = [25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35]
py_dev_y = [45372, 48876, 53850, 57287, 63016, 65998, 70003, 70000, 71496, 75370, 83640]
plt.plot(py_dev_x, py_dev_y)

plt.xlabel("年龄")
plt.ylabel("年薪")
plt.title("年龄和薪水的关系")

plt.show()
```

在上面的代码中，我们添加了另外一组数据 `py_dev_x，py_dev_y`，并作折线图，折线添加之后的图形如下所示：

![[Pasted image 20220427114019.png]]

仔细观察代码我们可以发现，`dev_x` 和 `py_dev_x` 是相同的，为了代码的简洁，我们可以只保留一份，修改后的代码如下：

```python
from matplotlib import pyplot as plt

ages_x = [25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35]

dev_y = [38496, 42000, 46752, 49320, 53200, 56000, 62316, 64928, 67317, 68748, 73752]
plt.plot(ages_x, dev_y)

py_dev_y = [45372, 48876, 53850, 57287, 63016, 65998, 70003, 70000, 71496, 75370, 83640]
plt.plot(ages_x, py_dev_y)

plt.xlabel("年龄")
plt.ylabel("年薪")
plt.title("年龄和薪水的关系")

plt.show()
```

执行上述代码得到的图形和上面一样，如下所示：

![[Pasted image 20220427114216.png]]

这样图形中便包含了两条折线，而每条折线代表的含义并没有在图形中标识出来，这样我们便不能对两条折线进行区分，为了对两条折线进行区分，我们需要为两条折线分别加上标签，修改后的代码如下：

```python
from matplotlib import pyplot as plt

ages_x = [25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35]

dev_y = [38496, 42000, 46752, 49320, 53200, 56000, 62316, 64928, 67317, 68748, 73752]
plt.plot(ages_x, dev_y)

py_dev_y = [45372, 48876, 53850, 57287, 63016, 65998, 70003, 70000, 71496, 75370, 83640]
plt.plot(ages_x, py_dev_y)

plt.xlabel("年龄")
plt.ylabel("年薪")
plt.title("年龄和薪水的关系")

plt.legend(['全部开发者','Python开发者'])

plt.show()
```

上面代码中，我们通过 `legend()` 函数为两条折线添加了标签，执行代码得到的图形如下：

![[Pasted image 20220427114635.png]]

上面添加标签使用的是 `legend()` 函数，`legend()` 函数的参数为一个列表。这种方法的不方便之处在于，列表中元素的顺序需和折线的绘制顺序保持一致，不然会导致错乱。当我们改变折线的绘制顺序时，要同步改变作为 `legend()` 函数参数的列表中元素的顺序，下面来看另外一种方法，代码如下：

```python
from matplotlib import pyplot as plt

ages_x = [25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35]

dev_y = [38496, 42000, 46752, 49320, 53200, 56000, 62316, 64928, 67317, 68748, 73752]
plt.plot(ages_x, dev_y, label="全部开发者")

py_dev_y = [45372, 48876, 53850, 57287, 63016, 65998, 70003, 70000, 71496, 75370, 83640]
plt.plot(ages_x, py_dev_y, label="Python开发者")

plt.xlabel("年龄")
plt.ylabel("年薪")
plt.title("年龄和薪水的关系")

plt.legend()

plt.show()
```

上面的方法通过在 `plot()` 函数中添加参数 `label` 来实现标签的添加，添加过参数 `label` 后，我们同样需要调用 `legend()` 函数，否则标签不会显示出来，只不过此时调用 `legend()` 函数不需要传入参数。为折线添加完标签之后的图形如下图所示：

![[Pasted image 20220427115141.png]]

上面图形的样式都是默认的，可以通过参数来设置图形的样式，包括折线的颜色、形状以及粗细等，代码如下：

```python
from matplotlib import pyplot as plt

ages_x = [25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35]

dev_y = [38496, 42000, 46752, 49320, 53200, 56000, 62316, 64928, 67317, 68748, 73752]
plt.plot(ages_x, dev_y, label="全部开发者", color="blue", marker=".", linestyle="-")

py_dev_y = [45372, 48876, 53850, 57287, 63016, 65998, 70003, 70000, 71496, 75370, 83640]
plt.plot(ages_x, py_dev_y, label="Python开发者", color="green", marker=".", linestyle="--")

plt.xlabel("年龄")
plt.ylabel("年薪")
plt.title("年龄和薪水的关系")

plt.legend()

plt.show()
```

上面的代码中，我们通过 `color` 参数指定图形的颜色，`marker` 参数指定每个数据点的标记，`linestyle` 参数指定图形的形状。执行完上述代码后的图形如下图所示：

![[Pasted image 20220427134145.png]]

`color` 参数的值也可以是一个 `Hex` 值，`Hex` 值由六位十六进制数组成，前两位十六进制数代表红色的强度，中间两位十六进制数绿色的强度，最后两位十六进制数代表蓝色的强度，代码如下：

```python
from matplotlib import pyplot as plt

ages_x = [25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35]

dev_y = [38496, 42000, 46752, 49320, 53200, 56000, 62316, 64928, 67317, 68748, 73752]
plt.plot(ages_x, dev_y, label="全部开发者", color="#FF0000", marker=".", linestyle="-")

py_dev_y = [45372, 48876, 53850, 57287, 63016, 65998, 70003, 70000, 71496, 75370, 83640]
plt.plot(ages_x, py_dev_y, label="Python开发者", color="#00FF00", marker=".", linestyle="--")

plt.xlabel("年龄")
plt.ylabel("年薪")
plt.title("年龄和薪水的关系")

plt.legend()

plt.show()
```

上面的代码中，通过 `Hex` 值 `#FF0000` 指定颜色为红色，通过 `Hex` 值 `#00FF00` 指定颜色为绿色。执行完上述代码后的图形如下图所示：

![[Pasted image 20220427134409.png]]

我们还可以为图形加上网格线，代码如下：

```python
from matplotlib import pyplot as plt

ages_x = [25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35]

dev_y = [38496, 42000, 46752, 49320, 53200, 56000, 62316, 64928, 67317, 68748, 73752]
plt.plot(ages_x, dev_y, label="全部开发者", color="#FF0000", marker=".", linestyle="-")

py_dev_y = [45372, 48876, 53850, 57287, 63016, 65998, 70003, 70000, 71496, 75370, 83640]
plt.plot(ages_x, py_dev_y, label="Python开发者", color="#00FF00", marker=".", linestyle="--")

plt.xlabel("年龄")
plt.ylabel("年薪")
plt.title("年龄和薪水的关系")

plt.legend()

plt.grid(True)

plt.show()
```

上面代码中，调用 `grid()` 函数并传入 True 参数，执行完上述代码后的图形如下图所示：

![[Pasted image 20220427134535.png]]

以上便是折线图的绘制方法。它的适用场景为同一变量随时间或有序类别而变化的趋势，例如上面的例子中薪水随年龄的变化趋势。不适用场景包括：1.x 轴节点过多；2.数据样本过多，导致折线堆积，难以聚焦到重点；3.变量数值大多数情况下为 0。
## 3. 条形图
条形图（bar chart）是用相同宽度的条形的高度或长短来表示数据多少的图形，是一种用于对不同类别进行数值比较的统计图表。条形图可以横置或纵置，纵置时也称为柱形图（column chart）。条形图被误用的一个典型代表就是篡改 `y` 轴，对读者视觉造成误导。在使用条形图时，务必要是原点位于 0。此外，注意对条形图进行排序。依据可视化的目的、以及想突出的重点信息，确定合理的排序标准，避免条形图看起来杂乱无章。

下面通过具体的示例介绍条形图的绘制，代码如下：

```python
from matplotlib import pyplot as plt

ages_x = [25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35]

dev_y = [38496, 42000, 46752, 49320, 53200, 56000, 62316, 64928, 67317, 68748, 73752]
plt.bar(ages_x, dev_y, label="全部开发者")

plt.xlabel("年龄")
plt.ylabel("年薪")
plt.title("年龄和薪水的关系")

plt.legend()

plt.show()
```

在上面的代码中，绘制条形图使用 `bar()` 函数，执行完上述代码得到的图形如下所示：

![[Pasted image 20220427140354.png]]

上面图形中只包含一类数据的条形图，和折线图一样，我们可以在一个图形中作多类数据的条形图，代码例如：

```python
from matplotlib import pyplot as plt

ages_x = [25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35]

dev_y = [38496, 42000, 46752, 49320, 53200, 56000, 62316, 64928, 67317, 68748, 73752]
py_dev_y = [45372, 48876, 53850, 57287, 63016, 65998, 70003, 70000, 71496, 75370, 83640]

plt.bar(ages_x, dev_y, label="全部开发者")
plt.bar(ages_x, py_dev_y, label="Python开发者")

plt.xlabel("年龄")
plt.ylabel("年薪")
plt.title("年龄和薪水的关系")

plt.legend()

plt.show()
```

在上面的代码中，我们又添加了一类数据的条形图，执行完上述代码，得到的图形如下所示：

![[Pasted image 20220427140635.png]]

从上述图形中，我们可以发现，虽然我们作了两类数据的条形图，但是只显示出一类数据的条形图，这是因为另一类数据的条形图被覆盖了。接下来，我们来解决这个问题，代码如下：

```python
import numpy as np
from matplotlib import pyplot as plt

ages_x = [25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35]
x_indexes = np.arange(len(ages_x))
width = 0.33

dev_y = [38496, 42000, 46752, 49320, 53200, 56000, 62316, 64928, 67317, 68748, 73752]
py_dev_y = [45372, 48876, 53850, 57287, 63016, 65998, 70003, 70000, 71496, 75370, 83640]

plt.bar(x_indexes - 0.5*width, dev_y, width=width, label="全部开发者")
plt.bar(x_indexes + 0.5*width, py_dev_y, width=width, label="Python开发者")

plt.xlabel("年龄")
plt.ylabel("年薪")
plt.title("年龄和薪水的关系")

plt.legend()

plt.show()
```

在上面的代码中，我们创建了一个和列表 `ages_x` 长度相同的数组 `x_indexes`，在作图时，用数组 `x_indexes` 替换横坐标。一类数据的横坐标为 `x_indexes` 中每个元素减去 `0.5*width`，另一类数据的横坐标为 `x_indexes` 中每个元素加上 `0.5*width`，另外在调用 `bar()` 函数时，传入 `width` 参数，表示条形图的宽度。执行完上述代码后的图形如下所示：

![[Pasted image 20220427141232.png]]

仔细观察上述图形，虽然我们将两类数据的条形图分开了，但是横坐标的数据同时也变成了 0~10，这显然是不正确的，因为原来的横坐标为表示年龄的数据，下面我们来解决这个问题，代码如下：

```python
import numpy as np
from matplotlib import pyplot as plt

ages_x = [25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35]
x_indexes = np.arange(len(ages_x))
width = 0.33

dev_y = [38496, 42000, 46752, 49320, 53200, 56000, 62316, 64928, 67317, 68748, 73752]
py_dev_y = [45372, 48876, 53850, 57287, 63016, 65998, 70003, 70000, 71496, 75370, 83640]

plt.bar(x_indexes-0.5*width, dev_y, width=width, label="全部开发者")
plt.bar(x_indexes+0.5*width, py_dev_y, width=width, label="Python开发者")

plt.xlabel("年龄")
plt.ylabel("年薪")
plt.title("年龄和薪水的关系")

plt.legend()

plt.xticks(ticks = x_indexes, labels = ages_x)

plt.show()
```

上面代码中，我们使用 `xticks()` 函数将 `x_indexes` 替换为 `ages_x`。执行完上述代码后的图形如下所示：

![[Pasted image 20220427141504.png]]

现在横坐标的数据变成了年龄。以上是垂直条形图的绘制，下面来介绍水平条形图的绘制，在介绍水平条形图的绘制方法之前，通过一个例子来看使用垂直条形图绘制会出现的问题。代码如下：

```python
import numpy as np
from matplotlib import pyplot as plt

languages = ['JavaScript', 'HTML/CSS', 'SQL', 'Python', 'Java', 'Bash/Shell/PowerShell', 
             'C#', 'PHP', 'C++','TypeScript']

popularity = [59219, 55466, 47544, 36443, 35917, 27097, 23030, 20524, 18523, 18017]

plt.bar(languages, popularity)

plt.title('最流行的编程语言')
plt.xlabel('编程语言')
plt.ylabel('流行度')


plt.show()
```

执行完上述代码后的图形如下所示：

![[Pasted image 20220427141914.png]]

从图中可以看出，横坐标上的数据标签已经重叠在一起了，下面我们使用水平条形图来改变这种情况，代码如下：

```python
import numpy as np
from matplotlib import pyplot as plt

languages = ['JavaScript', 'HTML/CSS', 'SQL', 'Python', 'Java', 'Bash/Shell/PowerShell', 
             'C#', 'PHP', 'C++','TypeScript']

popularity = [59219, 55466, 47544, 36443, 35917, 27097, 23030, 20524, 18523, 18017]

plt.barh(languages, popularity)

plt.title('最流行的编程语言')
plt.xlabel('流行度')
plt.ylabel('编程语言')

plt.show()
```

想要绘制水平的条形图，只需要将 `bar()` 函数改为 `barh()` 函数即可。执行完上述代码后生成的图形如下所示：

![[Pasted image 20220427142114.png]]

改成横置的条形图后，解决了标签重叠的问题。上面的图形中，最流行的语言在图形的最下面，一般情况下，我们希望最流行的语言在最上面，我们只需要对数据进行翻转即可，代码如下：

```python
import numpy as np
from matplotlib import pyplot as plt


languages = ['JavaScript', 'HTML/CSS', 'SQL', 'Python', 'Java', 'Bash/Shell/PowerShell', 
             'C#', 'PHP', 'C++','TypeScript']

popularity = [59219, 55466, 47544, 36443, 35917, 27097, 23030, 20524, 18523, 18017]

languages.reverse()
popularity.reverse()

plt.barh(languages, popularity)

plt.title('最流行的编程语言')
plt.xlabel('流行度')
plt.ylabel('编程语言')

plt.tight_layout()

plt.show()
```

上面的代码中，调用 `reverse()` 函数对列表 languages 和 popularity 进行翻转，执行完上述代码后生成的图形如下所示：

![[Pasted image 20220427142430.png]]

以上便是条形图的绘制方法，包括垂直条形图和水平条形图，它最适合对分类的数据进行比较。尤其是当数值比较接近时，由于人眼对于高度或长度的感知优于其他视觉元素（如面积、角度等），因此，适用条形图更加合适。由于条形图要求至少一个分类变量，它们之间是离散的，绘制条形图时，条形和条形之间有间隔。如果是连续变量，则应当使用直方图，绘制出每个区间的数值，条形之间是连续的、没有间隔。
## 4. 直方图
直方图，又称质量分布图，用于表示数据的分布情况，是一种常见的统计图表。一般用横轴表示数据区间，纵轴表示分布情况，柱子越高，则落在该区间的数量越大。直方图和条形图的外观相似。区别主要有以下几点：
+ 条形图用条形的长度（横置时）或高度（纵置时）表示各类别频数的多少，其宽度（表示类别）则是固定的；直方图是用面积表示各组频数的多少，矩形的高度表示每一组的频数或频率，宽度则表示各组的组距，因此其高度与宽度均有意义。
+ 由于分组数据具有连续性，直方图的各矩形通常是连续排列，而条形图则是分开排列。
+ 条形图主要用于展示分类数据的大小，而直方图则主要用于展示数值型数据的分布。

下面通过具体的示例介绍直方图的绘制，代码如下：

```python
import numpy as np
from matplotlib import pyplot as plt


ages = [18, 19, 21, 25, 26, 26, 30, 32, 38, 45, 55]

plt.hist(ages, bins=5)

plt.title('人员的年龄分布')
plt.xlabel('年龄')
plt.ylabel('人数')

plt.show()
```

上面的代码中，通过调用 `hist()` 函数来绘制直方图，`bins` 参数的含义是将整体数据分到几个区间内，在本例中，设置 `bins = 5`，表示将 `ages` 中的数据划分到 5 个区间内。执行完上述代码后生成的图形如下图所示：

![[Pasted image 20220427144141.png]]

直方图的高度表示每个区间的人数，虽然代码将数据划分到 5 个区间，但是从图形并不能明显看出每个区间的范围，下面我们为相邻区间加上一个分隔线，代码如下：

```python
import numpy as np
from matplotlib import pyplot as plt


ages = [18, 19, 21, 25, 26, 26, 30, 32, 38, 45, 55]

plt.hist(ages, bins=5, edgecolor='black')

plt.title('人员的年龄分布')
plt.xlabel('年龄')
plt.ylabel('人数')

plt.show()
```

上面的代码中，我们通过设置参数 `edgecolor` 为相邻区间加上了一个分隔线，加上分隔线之后的图形如下所示：

![[Pasted image 20220427144726.png]]

上面的例子中，我们在调用 `hist()` 方法时，只传入了需要划分的区间的个数，并没有规定每个区间的范围，区间范围的划定是自动进行的，当然，我们也可以通过参数来明确指定每个区间的范围，代码如下：

```python
import numpy as np
from matplotlib import pyplot as plt


ages = [18, 19, 21, 25, 26, 26, 30, 32, 38, 45, 55]

bins = [10, 20, 30, 40, 50, 60]

plt.hist(ages, bins=bins, edgecolor='black')

plt.title('人员的年龄分布')
plt.xlabel('年龄')
plt.ylabel('人数')

plt.show()
```

在上面的代码中，我们通过一个列表来指定各个区间的范围，总共划分了 5 个区间，区间的范围分别是 `[10,20)，[20,30)，[30,40)，[40,50)，[50,60)`。年龄在 `[10,20)` 区间内的人数为 2，在 `[20,30)` 区间内的人数为 4，在 `[30,40)` 区间内的人数为 3，在 `[40,50)` 区间内的人数为 1，在 `[50,60)` 区间内的人数为 1。执行完上述代码后生成的图形如下图所示：

![[Pasted image 20220427145010.png]]

手动指定区间的好处是，如果我们不想要某个区间的数据，直接在 bins 参数中去掉就可以了，代码如下：

```python
import numpy as np
from matplotlib import pyplot as plt


ages = [18, 19, 21, 25, 26, 26, 30, 32, 38, 45, 55]

bins = [20, 30, 40, 50, 60]

plt.hist(ages, bins=bins, edgecolor='black')

plt.title('人员的年龄分布')
plt.xlabel('年龄')
plt.ylabel('人数')

plt.show()
```

在上面的代码中，我们去掉了 `[10,20)` 这个区间，得到的图形如下所示：

![[Pasted image 20220427145314.png]]

由于直方图描述的是数据的分布，有时候我们需要画出平均值的位置，代码如下：

```python
import numpy as np
from matplotlib import pyplot as plt


ages = [18, 19, 21, 25, 26, 26, 30, 32, 38, 45, 55]

bins = [10, 20, 30, 40, 50, 60]

plt.hist(ages, bins=bins, edgecolor='black')

avg_age = 30.5

plt.axvline(avg_age, color='red', linewidth=2, label='平均值')

plt.title('人员的年龄分布')
plt.xlabel('年龄')
plt.ylabel('人数')

plt.legend()
plt.show()
```

在上面的代码中，我们通过 `axvline()` 来画出表示平均值的一条垂直的线，得到的图形如下所示：

![[Pasted image 20220427145526.png]]

在上图中，垂直的红线代表的是平均值。以上便是直方图的绘制方法，它的适用场景包括房价分布，人口年龄分布等。
## 5. 散点图
散点图，又名点图、散布图、X-Y图，英文 `Scatter plot` 或 `Scatter gram`。散点图将所有的数据以点的形式展现在平面直角坐标系上。它至少需要两个不同变量，一个沿 `x` 轴绘制，另一个沿 `y` 轴绘制。每个点在 `x、y` 轴上都有一个确定的位置。众多的散点叠加后，有助于展示数据集的“整体景观”，从而帮助我们分析两个变量之间的相关性，或找出趋势和规律。

散点图常被用于分析变量之间的相关性。如果两个变量的散点看上去都在一条直线附近波动，则称变量之间是线性相关的；如果所有点看上去都在某条曲线（非直线）附近波动，则称此相关为非线性相关的；如果所有点在图中没有显示任何关系，则称变量间是不相关的。

下面通过具体的示例介绍直方图的绘制，代码如下：

```python
import matplotlib.pyplot as plt


price = [2.50, 1.23, 4.02, 3.25, 5.00, 4.40]
sales_per_day = [34, 62, 49, 22, 13, 19]

plt.scatter(price, sales_per_day)

plt.title('价格和销量的关系')
plt.xlabel('价格')
plt.ylabel('销量')

plt.show()
```

散点图的绘制使用 `scatter()` 函数，代码执行后得到的图形如下所示：

![[Pasted image 20220427151955.png]]

`x` 轴表示商品的价格，`y` 轴表示商品的销量，每个点表示一组数据。上面点的样式是默认的，我们可以通过设置参数的方式来改变点的样式，例如大小、颜色、形状等，代码如下：

```python
import matplotlib.pyplot as plt


price = [2.50, 1.23, 4.02, 3.25, 5.00, 4.40]
sales_per_day = [34, 62, 49, 22, 13, 19]

plt.scatter(price, sales_per_day, s=100, c='green', marker='*')

plt.title('价格和销量的关系')
plt.xlabel('价格')
plt.ylabel('销量')

plt.show()
```

上面的代码中，我们通过参数 `s` 设置了点的大小，`c` 设置了点的颜色，`marker` 设置了点的形状。执行完代码生成的图形如下所示：

![[Pasted image 20220427152154.png]]

同样地，我们还可以参数设置点的边缘颜色，点的透明度，例如：

```python
import matplotlib.pyplot as plt


price = [2.50, 1.23, 4.02, 3.25, 5.00, 4.40]
sales_per_day = [34, 62, 49, 22, 13, 19]

plt.scatter(price, sales_per_day, s=100, c='green', edgecolors='black', linewidth=1, alpha=0.7)

plt.title('价格和销量的关系')
plt.xlabel('价格')
plt.ylabel('销量')

plt.show()
```

在上面的代码中，设置点的边缘的颜色为黑色，边缘线的粗细为 1，透明度设置成 0.7。执行完代码生成的图形如下所示：

![[Pasted image 20220427152444.png]]

上面的例子中，点的颜色是相同的，有时候我们需要根据另外一组数据来为点设置成不同的颜色，这样通过点的颜色便可以知道数据的大小，代码如下：

```python
import matplotlib.pyplot as plt


price = [2.50, 1.23, 4.02, 3.25, 5.00, 4.40]
sales_per_day = [34, 62, 49, 22, 13, 19]

profit_margin = [20, 35, 40, 20, 27.5, 15]

plt.scatter(price, sales_per_day, s=100, c=profit_margin, cmap='Greens', edgecolors='black', linewidth=1, alpha=0.7)

plt.title('价格和销量的关系')
plt.xlabel('价格')
plt.ylabel('销量')

plt.show()
```

在上面的代码中，我们添加了一组代表利润率的数据 `profit_margin`，在绘制图形时，将参数 c 设置成 `profit_margin`，这样每个点都有一个自己的颜色值。代码执行后得到的图形如下所示：

![[Pasted image 20220427152744.png]]

上图中，颜色越深代表值越大，虽然从数据我们可以知道颜色越深代表值越大，但是为了让图形传达的信息更加精确，需要明确标识颜色和值的对应关系，代码如下：

```python
import matplotlib.pyplot as plt


price = [2.50, 1.23, 4.02, 3.25, 5.00, 4.40]
sales_per_day = [34, 62, 49, 22, 13, 19]

profit_margin = [20, 35, 40, 20, 27.5, 15]

plt.scatter(price, sales_per_day, s=100, c=profit_margin, cmap='Greens', 
            edgecolors='black', linewidth=1, alpha=0.7)

cbar = plt.colorbar()
cbar.set_label('利润率')

plt.title('价格和销量的关系')
plt.xlabel('价格')
plt.ylabel('销量')

plt.show()
```

上面的代码中，通过 `colorbar()` 函数设置了色卡。代码执行后得到的图形如下所示：

![[Pasted image 20220427152934.png]]

上面是通过颜色的深浅来代表值的大小，在用颜色的深浅来代表值的大小的同时，我们还可以根据数据来设置点的大小，代码如下：

```python
import matplotlib.pyplot as plt
import numpy as np


price = np.array([2.50, 1.23, 4.02, 3.25, 5.00, 4.40])
sales_per_day = np.array([34, 62, 49, 22, 13, 19])

profit_margin = np.array([20, 35, 40, 20, 27.5, 15])

plt.scatter(price, sales_per_day, s=profit_margin*10, c=profit_margin, cmap='Greens', 
            edgecolors='black', linewidth=1, alpha=0.7)

cbar = plt.colorbar()
cbar.set_label('利润率')

plt.title('价格和销量的关系')
plt.xlabel('价格')
plt.ylabel('销量')

plt.show()
```

上面的代码中，将点的大小设置成 `profit_margin * 10`，这样点的大小便和利润率成正比。代码执行后得到的图形如下所示：

![[Pasted image 20220427153115.png]]

上面的例子中只包含一组数据，在同一个图形中可以包含多组数据的散点图，代码如下：

```python
import matplotlib.pyplot as plt
import numpy as np


price_orange = np.array([2.50, 1.23, 4.02, 3.25, 5.00, 4.40])
sales_per_day_orange = np.array([34, 62, 49, 22, 13, 19])
profit_margin_orange = np.array([20, 35, 40, 20, 27.5, 15])

price_cereal = np.array([1.50, 2.50, 1.15, 1.95])
sales_per_day_cereal = np.array([67, 34, 36, 12])
profit_margin_cereal = np.array([20, 42.5, 33.3, 18])

plt.scatter(price_orange, sales_per_day_orange, s=profit_margin_orange*10, c=profit_margin_orange, 
            cmap='jet', edgecolors='black', linewidth=1, alpha=0.7, label='orange')


plt.scatter(price_cereal, sales_per_day_cereal, s=profit_margin_cereal*10, c=profit_margin_cereal, 
            cmap='jet', edgecolors='black', linewidth=1, alpha=0.7, marker='d', label='cereal')

cbar = plt.colorbar()
cbar.set_label('利润率')

plt.title('价格和销量的关系')
plt.xlabel('价格')
plt.ylabel('销量')

plt.legend()
plt.show()
```

在上面的代码中，我们又添加了一组数据的点图，代码执行后得到的图形如下所示：

![[Pasted image 20220427153418.png]]

以上便是散点图的绘制。

散点图的适用场景：
+ 适用于分析变量之间是否存在某种关系或相关性。
+ 适用于分析变量之间相关性的强弱，我们可以通过查看图上数据点的密度来确定相关性的强弱。
+ 适用于在不考虑时间的情况下比较大量的数据点，数据点越多，比较的效果就越明显。

散点图的不适用场景：
+ 对于数据量较少的数据集不建议使用，分析结果会存在较大的偶然性。
+ 不适用于数据点过大、过多的情况，会影响图表的可读性，导致无法进行分析。可以通过减小点的大小、调整透明度、减少数据量、数据分组、建立3D模型等等的方法进行优化。
+ 数据分类过多，无法快速识别，失去可视化的意义和价值。
+ 通过观察散点图得出的变量之间的相关性并不等同于确定的因果关系。

## 6. 饼图
饼图，或称饼状图，是一个将圆形划分为几个扇形的统计图表。在饼图中，每个扇形的弧长大小，表示该种类占总体的比例，这些扇形合在一起刚好是一个完整的圆形。

饼图最显著的功能在于表现”占比“。习惯上，人们也用饼图来比较扇形的大小，从而获得对数据的认知。但是，由于人类对“角度”的感知力并不如“长度”，在需要准确的表达数值（尤其是当数值接近、或数值很多）时，饼图常常不能胜任，建议用柱状图代替。

使用时，须确认各个扇形的数据加起来等于 100%；避免扇区超过 5 个，尽量让图表简洁明了。

下面通过具体的示例介绍饼图的绘制，代码如下：

```python
import matplotlib.pyplot as plt


languages = ['JavaScript', 'HTML/CSS', 'SQL', 'Python', 'Java']
popularity = [59219, 55466, 47544, 36443, 35917]

plt.pie(popularity)

plt.show()
```

在上面的代码中，我们只要将一个列表传入到 `pie()` 函数中，便可以绘制一个饼图。代码执行后得到的图形如下所示：

![[Pasted image 20220427154431.png]]

从上面的饼图中我们不知道每个扇形所代表的数据，下面来为每个扇形打上标签。

```python
import matplotlib.pyplot as plt


languages = ['JavaScript', 'HTML/CSS', 'SQL', 'Python', 'Java']
popularity = [59219, 55466, 47544, 36443, 35917]

plt.pie(popularity, labels=languages)

plt.show()
```

为了给每个扇形打上标签，我们只需要传入参数 `labels` 即可。代码执行后得到的图形如下所示：

![[Pasted image 20220427154556.png]]

除了给每个扇形打上标签之外，我们还可以把每个扇形的占比标在图形上，代码如下：

```python
import matplotlib.pyplot as plt


languages = ['JavaScript', 'HTML/CSS', 'SQL', 'Python', 'Java']
popularity = [59219, 55466, 47544, 36443, 35917]

plt.pie(popularity, labels=languages, autopct='%1.1f%%')

plt.show()
```

上面的代码中，我们通过参数 autopct 为每个扇形标上占比。代码执行后得到的图形如下所示：

![[Pasted image 20220427154715.png]]

上图中扇形从大到小排列的方向是逆时针的，一般情况下，我们比较习惯顺时针的方向，下面我们通过参数来设置成顺时针方向，代码如下：

```python
import matplotlib.pyplot as plt


languages = ['JavaScript', 'HTML/CSS', 'SQL', 'Python', 'Java']
popularity = [59219, 55466, 47544, 36443, 35917]

plt.pie(popularity, labels=languages, autopct='%1.1f%%', counterclock=False, startangle=90)

plt.title('top5 编程语言占比')
plt.show()
```

上面代码中，通过设置参数 `counterclock` 为 `False`，使得方向改为顺时针方向，通过设置参数 `startangle` 为 90，将最大扇形放在 12 点钟方向。代码执行后得到的图形如下所示：

![[Pasted image 20220427154837.png]]

有时候，为了强调某一个扇形，我们会让这个扇形脱离整个圆形，代码如下：

```python
import matplotlib.pyplot as plt


languages = ['JavaScript', 'HTML/CSS', 'SQL', 'Python', 'Java']
popularity = [59219, 55466, 47544, 36443, 35917]

plt.pie(popularity, labels=languages, autopct='%1.1f%%', 
        counterclock=False, startangle=90,explode=[0,0,0.1,0,0])

plt.title('top5 编程语言占比')
plt.show()
```

在上面的代码中，我们通过设置参数 `explode` 来强调 `SQL` 这个扇形，要强调那个扇形，就把相应的值设置成非 0。代码执行后得到的图形如下所示：

![[Pasted image 20220427154957.png]]

以上便是饼图的绘制方法。
饼图的适用场景：
+ 想要突出表示某个部分在整体中所占比例，尤其该部分所占比例达到总体的25%或50%时。
+ 分类数量最好小于5个。
+ 各不同分类间的占比差异明显。
+ 需要确定的图表绘制空间大小（不会随着分类增多有增大画布空间）。

饼图的不适用场景：
+ 如果变量之间相互独立，并不构成一个整体，那么不可以使用饼图。
+ 饼图不能用来表现趋势。
+ 由于饼图用面积取代了长度，从而加大了对各个数据进行比较的难度。因此，当需要对数据进行比较，分清孰大孰小，尤其是当数据接近时，条形图更加合适。
+ 当类别过多时，不建议使用饼图，否则阅读将会很差。

## 7. 热力图
热力图是一种通过对色块着色来显示数据的统计图表。绘图时，需指定颜色映射的规则。例如，较大的值由较深的颜色表示，较小的值由较浅的颜色表示；较大的值由偏暖的颜色表示，较小的值由较冷的颜色表示，等等。

从数据结构来划分，热力图一般分为两种。第一，表格型热力图，也称色块图。它需要 2 个分类字段和 1 个数值字段，分类字段确定 x、y 轴，将图表划分为规整的矩形块。数值字段决定了矩形块的颜色。第二，非表格型热力图，或曰平滑的热力图，它需要 3 个数值字段，可绘制在平行坐标系中（2个数值字段分别确定x、y轴，1个数值字段确定着色）。

热力图适合用于查看总体的情况、发现异常值、显示多个变量之间的差异，以及检测它们之间是否存在任何相关性。

下面通过具体的示例介绍热力图的绘制，代码如下：

```python
import matplotlib.pyplot as plt
import numpy as np

harvest = np.array([[0.8, 2.4, 2.5, 3.9, 0.0, 4.0, 0.0],
                    [2.4, 0.0, 4.0, 1.0, 2.7, 0.0, 0.0],
                    [1.1, 2.4, 0.8, 4.3, 1.9, 4.4, 0.0],
                    [0.6, 0.0, 0.3, 0.0, 3.1, 0.0, 0.0],
                    [0.7, 1.7, 0.6, 2.6, 2.2, 6.2, 0.0],
                    [1.3, 1.2, 0.0, 0.0, 0.0, 3.2, 5.1],
                    [0.1, 2.0, 0.0, 1.4, 0.0, 1.9, 6.3]])

plt.imshow(harvest)
plt.show()
```

在上面的代码中，将一个二维数组传入到 `imshow()` 方法中便可以绘制一个热力图，每个色块的颜色代表数据的大小。代码执行后得到的图形如下所示：

![[Pasted image 20220427164408.png]]

上面只是绘制了色块，并没有指明 `x` 轴 和 `y` 轴代表的含义，下面我们加上 `x` 轴和 `y` 轴的标签，并加上标题，代码如下：

```python
import matplotlib.pyplot as plt
import numpy as np

vegetables = ["cucumber", "tomato", "lettuce", "asparagus",
              "potato", "wheat", "barley"]
farmers = ["Farmer Joe", "Upland Bros.", "Smith Gardening",
           "Agrifun", "Organiculture", "BioGoods Ltd.", "Cornylee Corp."]

harvest = np.array([[0.8, 2.4, 2.5, 3.9, 0.0, 4.0, 0.0],
                    [2.4, 0.0, 4.0, 1.0, 2.7, 0.0, 0.0],
                    [1.1, 2.4, 0.8, 4.3, 1.9, 4.4, 0.0],
                    [0.6, 0.0, 0.3, 0.0, 3.1, 0.0, 0.0],
                    [0.7, 1.7, 0.6, 2.6, 2.2, 6.2, 0.0],
                    [1.3, 1.2, 0.0, 0.0, 0.0, 3.2, 5.1],
                    [0.1, 2.0, 0.0, 1.4, 0.0, 1.9, 6.3]])

plt.xticks(np.arange(len(farmers)), labels=farmers, 
                     rotation=45, rotation_mode="anchor", ha="right")
plt.yticks(np.arange(len(vegetables)), labels=vegetables)    

plt.title("Harvest of local farmers (in tons/year)")

plt.imshow(harvest)
plt.tight_layout()
plt.show()
```

上面代码中，`x` 轴代表农场主的姓名，`y` 轴代表蔬菜的名称，二维数组中的数据代表某个农场主种的某类蔬菜的产量。代码执行后得到的图形如下所示：

![[Pasted image 20220427164718.png]]

上图中，我们加上了 `x` 轴和 `y` 轴代表的含义以及整个图的标题，但是现在我们还不知道不同色块所对应的数值的大小，下面我们就来加上。

```python
import matplotlib.pyplot as plt
import numpy as np

vegetables = ["cucumber", "tomato", "lettuce", "asparagus",
              "potato", "wheat", "barley"]
farmers = ["Farmer Joe", "Upland Bros.", "Smith Gardening",
           "Agrifun", "Organiculture", "BioGoods Ltd.", "Cornylee Corp."]

harvest = np.array([[0.8, 2.4, 2.5, 3.9, 0.0, 4.0, 0.0],
                    [2.4, 0.0, 4.0, 1.0, 2.7, 0.0, 0.0],
                    [1.1, 2.4, 0.8, 4.3, 1.9, 4.4, 0.0],
                    [0.6, 0.0, 0.3, 0.0, 3.1, 0.0, 0.0],
                    [0.7, 1.7, 0.6, 2.6, 2.2, 6.2, 0.0],
                    [1.3, 1.2, 0.0, 0.0, 0.0, 3.2, 5.1],
                    [0.1, 2.0, 0.0, 1.4, 0.0, 1.9, 6.3]])

plt.xticks(np.arange(len(farmers)), labels=farmers, 
                     rotation=45, rotation_mode="anchor", ha="right")
plt.yticks(np.arange(len(vegetables)), labels=vegetables)    
plt.title("Harvest of local farmers (in tons/year)")

plt.imshow(harvest)
plt.colorbar()
plt.tight_layout()
plt.show()
```

上面的代码中，我们通过调用 `colorbar()` 函数来加上数值和颜色的对应规则。代码执行后得到的图形如下所示：

![[Pasted image 20220427170030.png]]

上图我们便加上了颜色和数值的对应规则。接下来我们再为每个色块加上所代表的数值，代码如下：

```python
import matplotlib.pyplot as plt
import numpy as np

vegetables = ["cucumber", "tomato", "lettuce", "asparagus",
              "potato", "wheat", "barley"]
farmers = ["Farmer Joe", "Upland Bros.", "Smith Gardening",
           "Agrifun", "Organiculture", "BioGoods Ltd.", "Cornylee Corp."]

harvest = np.array([[0.8, 2.4, 2.5, 3.9, 0.0, 4.0, 0.0],
                    [2.4, 0.0, 4.0, 1.0, 2.7, 0.0, 0.0],
                    [1.1, 2.4, 0.8, 4.3, 1.9, 4.4, 0.0],
                    [0.6, 0.0, 0.3, 0.0, 3.1, 0.0, 0.0],
                    [0.7, 1.7, 0.6, 2.6, 2.2, 6.2, 0.0],
                    [1.3, 1.2, 0.0, 0.0, 0.0, 3.2, 5.1],
                    [0.1, 2.0, 0.0, 1.4, 0.0, 1.9, 6.3]])

plt.xticks(np.arange(len(farmers)), labels=farmers, 
                     rotation=45, rotation_mode="anchor", ha="right")
plt.yticks(np.arange(len(vegetables)), labels=vegetables)    
plt.title("Harvest of local farmers (in tons/year)")

for i in range(len(vegetables)):
    for j in range(len(farmers)):
        text = plt.text(j, i, harvest[i, j], ha="center", va="center", color="w")

plt.imshow(harvest)
plt.colorbar()
plt.tight_layout()
plt.show()
```

上面的代码中，我们通过一个循环来为每个色块加上对应的数值。代码执行后得到的图形如下所示：

![[Pasted image 20220427170128.png]]

以上便是热力图的绘制方法。

热力图的适用场景为：
+ 热力图的优势在于“空间利用率高”，可以容纳较为庞大的数据。热力图不仅有助于发现数据间的关系、找出极值，也常用于刻画数据的整体样貌，方便在数据集之间进行比较（例如将每个运动员的历年成绩都浓缩成一张热力图，再进行比较）。
+ 如果将某行或某列设置为时间变量，热力图也可用于展示数据随时间的变化。例如，用热力图来反映一个城市一年中的温度变化，气候的冷暖走向，一目了然。

热力图的不适用场景为：
+ 尽管热力图能够容纳较多的数据，但反过来说，人们很难将其中的色块转换为精确的数字。因此，当需要清楚知道数值的时候，可能需要额外的标注。

## 8. 堆叠条形图
堆叠条形图是一种用来分解整体、比较各部分的图。与条形图类似，堆叠条形图常被用于比较不同类别的数值。而且，它的每一类数值内部，又被划分为多个子类别，这些子类别一般用不同的颜色来表示。

如果说条形图可以帮助我们观察总量，那么堆叠条形图则可以同时反映总量与结构，即总量是多少？它又是由哪些部分构成的？进而，我们还可以探究哪一部分比例最大，以及每一部分的变动情况等等。

下面通过具体的示例介绍堆叠条形图的绘制，代码如下：

```python
import matplotlib.pyplot as plt
import numpy as np


x = ['A', 'B', 'C', 'D']
y1 = np.array([10, 20, 10, 30])
y2 = np.array([20, 25, 15, 25])
y3 = np.array([12, 15, 19, 6])
y4 = np.array([10, 29, 13, 19])
  
plt.bar(x, y1, label='Round1', width=0.67)
plt.bar(x, y2, bottom=y1, label='Round2', width=0.67)
plt.bar(x, y3, bottom=y1+y2, label='Round3', width=0.67)
plt.bar(x, y4, bottom=y1+y2+y3, label='Round4', width=0.67)

plt.xlabel("Teams")
plt.ylabel("Score")
plt.legend()
plt.title("Scores by Teams in 4 Rounds")

plt.tight_layout()
plt.show()
```

在上面的代码中，列表 `x` 代表 4 只队伍，列表 `y1、y2、y3` 和 `y4` 分别表示 4 只队伍在 4 局比赛的得分。在进行图形绘制时，在绘制 `y2` 数据时，设置 `bottom = y1`，意思是在 `y1` 数据绘制的条形图的基础进行绘制，也就是形成堆叠图。代码执行完得到的图形如下所示：

![[Pasted image 20220427170751.png]]

在上图中，y1 列表对应的条形图在最底部，y2 列表对应的条形图位于 y1 列表对应条形图的上面，后面以此类推。上面的堆叠条形图是垂直方向的，和前面的条形图一样，我们同样的可以绘制水平方向的堆叠条形图，代码如下：

```python
import matplotlib.pyplot as plt
import numpy as np

  
x = ['A', 'B', 'C', 'D']
y1 = np.array([10, 20, 10, 30])
y2 = np.array([20, 25, 15, 25])
y3 = np.array([12, 15, 19, 6])
y4 = np.array([10, 29, 13, 19])
  
plt.barh(x, y1, label='Round1', height=0.67)
plt.barh(x, y2, left=y1, label='Round2', height=0.67)
plt.barh(x, y3, left=y1+y2, label='Round3', height=0.67)
plt.barh(x, y4, left=y1+y2+y3, label='Round4', height=0.67)

plt.xlabel("Score")
plt.ylabel("Teams")
plt.legend()
plt.title("Scores by Teams in 4 Rounds")

plt.tight_layout()
plt.show()
```

在绘制水平方向的堆叠条形图时，需要将参数 `bottom` 改为 `left`，将参数 `width` 改为 `height`，需要将 `x` 轴标签改为 `Score`，`y` 轴标签改为 `Teams`。其他的和垂直方向的堆叠条形图的绘制类似。代码执行后得到的图形如下所示：

![[Pasted image 20220427171018.png]]

以上便是堆叠条形图的绘制。

堆叠条形图的适用场景：
对比不同类别数据的数值大小，同时对比每一类别数据中，子类别的构成及大小。

堆叠条形图的不适用场景：
+ 对于堆叠柱状图来说，很多色块不处于同一水平线上，因此难以比较。所以，如果需要清楚的比较数值，建议采用分组柱状图，让每一根柱子的高度都显而易见。
+ 当堆叠的类型过多，很容易让人眼花缭乱。
## 9. 子图
前面讲述的图表绘制方法一次只会绘制一张图表，但是有些情况下，我们希望把一组图放在一起进行比较，有没有什么好的方法呢？`matplotlib` 中提供的 `subplots()` 可以很好的解决这个问题。通过调用 `subplots()` 可以将整个绘图区域分成 m * n 个子区域，每个子区域都可以绘制一个子图。

当 m = 1，n = 2 时，绘图区域的划分情况如下所示：

![[Pasted image 20220427171802.png]]

当 m = 2，n = 1 时，绘图区域的划分情况如下所示：

![[Pasted image 20220427171836.png]]

当 m = 2，n = 2 时，绘图区域的划分情况如下所示：

![[Pasted image 20220427171857.png]]

下面就通过例子来看 `subplots()` 的使用，代码如下：

```python
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 2*np.pi, 400)
y = np.sin(x)

fig, ax = plt.subplots()
ax.plot(x, y)
ax.set_title('plot sin')

plt.show()
```

在上面的代码中，调用 `subplots()`` 函数时，没有传入参数，这样在默认情况下整个绘图区域只会包含一个子区域。`subplots()`` 函数会返回两个值，一个是 fig，一个是 ax。接下来便可以使用 ax 对子图进行绘制。代码执行后得到的图形如下所示：

![[Pasted image 20220427172244.png]]

上面的绘制只包含一个图形，下面来看包含多个子图的绘制，代码如下：

```python
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 2*np.pi, 400)
y1 = np.sin(x)
y2 = np.cos(x)

fig, ax = plt.subplots(nrows=2, ncols=1)

ax[0].plot(x, y1)
ax[0].set_title('plot sin')

ax[1].plot(x, y2)
ax[1].set_title('plot cos')

plt.show()
```

上面代码中，向 `subplots()` 函数传入参数 nrows 和 ncols，值分别为 2 和 1。这样整个绘图区域会被划分为两个子区域。返回值 ax 为包含两个子区域对象的数组，我们可以使用索引的方式来访问每个对象，下面便可以使用这两个对象进行绘图。代码执行后得到的图形如下所示：

![[Pasted image 20220427172452.png]]

由于两个子图的横坐标相同，这样可以让两个子图共享横坐标，代码如下：

```python
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 2*np.pi, 400)
y1 = np.sin(x)
y2 = np.cos(x)


fig, ax = plt.subplots(nrows=2, ncols=1, sharex=True)

ax[0].plot(x, y1)
ax[0].set_title('plot sin')

ax[1].plot(x, y2)
ax[1].set_title('plot cos')

plt.show()
```

为了让两个子图共享横坐标，只需要在调用 subplots() 函数时传入参数 sharex，并设置其值为 True。代码执行后得到的图形如下所示：

![[Pasted image 20220427172623.png]]

上面两个子图是上下排列，我们再来看看左右排列的情况，代码如下：

```python
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 2*np.pi, 400)
y1 = np.sin(x)
y2 = np.cos(x)


fig, ax = plt.subplots(nrows=1, ncols=2)

ax[0].plot(x, y1)
ax[0].set_title('plot sin')

ax[1].plot(x, y2)
ax[1].set_title('plot cos')

plt.show()
```

为了让两个子图左右排列，只需要将参数 nrows 和 ncols 的值分别设置为 1 和 2。代码执行后得到的图形如下所示：

![[Pasted image 20220427172728.png]]

上面图形中的子图长和宽不是很协调，下面我们通过参数来调整图形的长和宽的比例，代码如下：

```python
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 2*np.pi, 400)
y1 = np.sin(x)
y2 = np.cos(x)


fig, ax = plt.subplots(nrows=1, ncols=2, figsize=(18,5))

ax[0].plot(x, y1)
ax[0].set_title('plot sin')

ax[1].plot(x, y2)
ax[1].set_title('plot cos')

plt.show()
```

上面的代码中，在调用 `subplots()` 函数时，传入参数 figsize 来设置图形的长和宽。代码执行后得到的图形如下图所示：

![[Pasted image 20220427172841.png]]

上面图形中，两个子图左右排列而且纵坐标轴相同，这样我们可以设置让两个子图共享纵坐标轴，代码如下：

```python
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 2*np.pi, 400)
y1 = np.sin(x)
y2 = np.cos(x)


fig, ax = plt.subplots(nrows=1, ncols=2, figsize=(18,5), sharey=True)

ax[0].plot(x, y1)
ax[0].set_title('plot sin')

ax[1].plot(x, y2)
ax[1].set_title('plot cos')

plt.show()
```

为了让两个子图共享纵坐标轴，只需要向 `subplots()` 函数传入 sharey 参数，并设置其值为 True，代码执行后得到的图形如下所示：

![[Pasted image 20220427172943.png]]

上面的例子中，调用 `subplots()` 函数返回的是一维数组，下面我们来看一个返回多维数组的例子：

```python
import matplotlib.pyplot as plt
import numpy as np

x1 = np.linspace(0, 2*np.pi, 400)
y1 = np.sin(x1)
y2 = np.cos(x1)

x2 = np.linspace(0, 2*np.pi, 40)
y3 = np.sin(x2)
y4 = np.cos(x2)

fig, ax = plt.subplots(nrows=2, ncols=2)

ax[0,0].plot(x1, y1)
ax[0,0].set_title('plot sin')

ax[0,1].plot(x1, y2)
ax[0,1].set_title('plot cos')

ax[1,0].scatter(x2, y3)
ax[1,0].set_title('plot scatter sin')

ax[1,1].scatter(x2, y4)
ax[1,1].set_title('plot scatter cos')

plt.show()
```

在上面的代码中，ax 是一个 2 * 2 的数组，所以在进行索引的时候，需要使用二维数组的索引方法。代码执行后得到的图形如下所示：

![[Pasted image 20220427173056.png]]

上面四个图，左右可以共享 y 轴的坐标，上下可以共享 x 轴的坐标，下面我们来设置共享坐标轴，代码如下：

```python
import matplotlib.pyplot as plt
import numpy as np

x1 = np.linspace(0, 2*np.pi, 400)
y1 = np.sin(x1)
y2 = np.cos(x1)

x2 = np.linspace(0, 2*np.pi, 40)
y3 = np.sin(x2)
y4 = np.cos(x2)

fig, ax = plt.subplots(nrows=2, ncols=2, sharex=True, sharey=True)

ax[0,0].plot(x1, y1)
ax[0,0].set_title('plot sin')

ax[0,1].plot(x1, y2)
ax[0,1].set_title('plot cos')

ax[1,0].scatter(x2, y3)
ax[1,0].set_title('plot scatter sin')

ax[1,1].scatter(x2, y4)
ax[1,1].set_title('plot scatter cos')

plt.show()
```

代码执行后得到的图形如下所示：

![[Pasted image 20220427173155.png]]

以上便是多个子图绘制的介绍。

# 第四章 线性代数
线性代数中最基础、最根源的组成部分就是向量。从物理学的视角看，向量是空间中的箭头，决定一个向量的是它的长度和它所指的方向，只要以上两个特征相同，可以自由移动一个向量而保持它不变。从计算机科学的视角看，向量是有序的数字列表。
## 1. 矩阵和向量
## 2. 加法和标量乘法
## 3. 矩阵向量乘法
## 4. 矩阵乘法
## 5. 矩阵乘法特征
## 6. 逆和转置
# 第五章 统计
[https://www.analyticsvidhya.com/blog/2021/04/statistics-and-probability-concepts-for-data-science/](https://www.analyticsvidhya.com/blog/2021/04/statistics-and-probability-concepts-for-data-science/)

[https://derangedphysiology.com/main/cicm-primary-exam/required-reading/research-methods-and-statistics/Chapter%203.0.2/variability-dispersion-and-central-tendency](https://derangedphysiology.com/main/cicm-primary-exam/required-reading/research-methods-and-statistics/Chapter%203.0.2/variability-dispersion-and-central-tendency)
## 1. 集中趋势
### 1.1 平均数
$$A=\frac{1}{n}\sum_{i=1}^na_i$$
### 1.2 中位数
### 1.3 众数
## 2. 分散趋势
### 2.1 范围
### 2.2 方差
### 2.3 标准差
### 2.4 百分位数
## 3. 协方差
### 3.1 关联
## 4. 辛普森悖论
# 第六章 概率
## 1. 独立与非独立
$$P(E,F) = P(E)P(F)$$
## 2. 条件概率
$$P(E|F) = P(E,F)/P(F)$$
## 3. 贝叶斯定理
$$P(E|F) = P(E,F)/P(F) = P(F|E)P(E)/P(F)$$
$$P(F) = P(F,E) + P(F,\overline{E})$$
$$P(E|F) = P(E,F)/P(F) = P(F|E)P(E)/(P(F,E) + P(F,\overline{E}))$$
## 4. 随机变量
## 5. 连续分布
### 5.1 概率密度函数
### 5.2 累积分布函数
## 6. 正态分布
$$f(x|\mu,\sigma)=\frac{1}{\sqrt{2\pi}\mu}exp(-\frac{(x-\mu)^2}{2\sigma^2})$$
## 7. 中心极限定理

# 第七章 假设与推理
## 1. 统计假设检验
### 1.1 虚假设
### 1.2 备择假设
## 2. p-值
## 3. 置信区间
## 4. p值操控
## 5. 贝叶斯推理
# 第八章 梯度下降
## 1. 梯度下降背后的思想
## 2. 梯度的计算
## 3. 使用梯度
## 4. 选择合适的步长
+ 使用固定的步长。
+ 随时间缩小步长。
## 5. 使用梯度下降训练模型
## 6. 小批量和随机梯度下降
# 第九章 获取数据
## 1. 标准输入和输出
## 2. 读取文件
## 3. 爬取网页数据
## 4. 使用 APIs
# 第十章 处理数据
## 1. 探索数据
## 2. 使用命名元组
## 3. 数据清洗和转换
## 4. 操作数据
## 5. 数据缩放
## 6. 
# 第十一章 机器学习
# 第十二章 K最近邻算法
# 第十三章 朴素贝叶斯
# 第十四章 简单线性回归
# 第十五章 多元回归
# 第十六章 逻辑回归
# 第十七章 决策树
# 第十八章 神经网络
# 第十九章 深度学习
# 第二十章 聚类
# 第二十一章 自然语言处理
# 第二十二章 网络分析
# 第二十三章 推荐系统
# 第二十四章 数据库和SQL
# 第二十五章 MapReduce
# 第二十六章 数据伦理

