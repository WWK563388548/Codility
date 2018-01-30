# Chapter 2 数组(Array)
<br>
&emsp;数组是一种数据结构，它经常被用于在一个容器中储存许多东西。想象一下我们有一个物品列表；比如，一个购物列表。我们不会将要买的商品写在许多张纸上；我们只会将它们列在一张纸上。一张纸就像一个数组。同样地，如果我们计划去记录一整年，365天，的气温，我们不需要创建许多独立的变量去存储每一天的数据，只需要将所有数据存入一个数组就可以了。
<br>

***
### 2.1 创建一个数组
&emsp;我们想去创建一个包含三种商品的购物清单。它就像下面这样被创建：
<br>
```python
shopping = ['bread', 'butter', 'cheese']
```
&emsp;(在这里，“shopping”是数组的名字，在数组中的每一种商品都被“,”所分隔开)。数组中的每样物品被叫做元素(element)。数组可以储存许多元素（假设我们有足够的内存）。注意，数组／python中的list也可以是空的：
<br>
```python
shopping = []
```
&emsp;如果计划去记录1整年，365天的气温，我们可以预先创造一个储存数据的容器。数组可以像下面这样创建：
<br>
```python
temperatures = [0] * 365
print(temperatures)
```
&emsp;(在这里，我们创建的数组包含了365个0)
<br>
***
### 2.2 访问数组的值
&emsp;数组提供了简单的方法去访问它的元素。在数组之中，每一个元素都被分配给了一个叫作索引的值。索引值是一组从0开始的，连续不断的整数。例如，在数组shopping = ['bread', 'butter', 'cheese']中，'bread'的索引值是0，'butter'的索引值是1，以及'cheese'的索引值是2。如果我们想去检查某个索引值上的元素是什么（例如，索引值1的元素），我们可以通过在中括号里指定索引值的方式来找到它。例如：shopping[1]。
<br>
***
### 2.3 修改数组的值
&emsp;我们也可以改变数组元素的值， 每一个数组元素都可以被单独赋值。例如， 我们想记录第42天的气温， 这一天的气温是25摄氏度。我们可以通过一次简单的赋值来完成它：
<br>
```python
temperatures[42] = 25
```
&emsp;如果我们要在购物列表中添加更多的产品， 可以像下面这样添加：
<br>
```python
shopping += ['eggs']
print(shopping)
```
元素的索引值也将自动添加（在这里， ‘eggs’的索引值是3）。
<br>
***
### 2.4 遍历一个数组
&emsp;我们经常需要去遍历一个数组的所有元素；或许是计算某个特定元素的数量。已知某个数组包含N个元素， 我们可以通过检查索引值来遍历数组， 索引值是从0到N-1。我们也可以通过len（）函数去获取数组的长度。例如， 我们可以快速计算购物列表中元素的数量， 就像下面这样： 
<br>
```python
N = len(shopping)
```
&emsp;我们来构造一个函数， 它可以计算气温在零下的日子的数量。
<br>
```python
temperatures = [5, 17, -16, -8, -7, 25, 14]

def negative(temperatures):
    N = len(temperatures)
    days = 0
    for i in range(N):
        if temperatures[i] < 0:
            days += 1

    return days

print(negative(temperatures))
```
&emsp;与其遍历索引值， 我们可以直接遍历数组的元素。 如果要这样做， 我们可以这样简单的写：
<br>
```python
for item in array:
    ...
```
让我们来简写上面的程序： 
<br>
```python
temperatures = [5, 17, -16, -8, -7, 25, 14]

def negative(temperatures):
    days = 0
    for t in temperatures:
        if t < 0:
           days += 1

    return days

print(negative(temperatures))
```
在上面的程序中， 数组中的数字如果小于0， days就会增加1。
<br>
***
