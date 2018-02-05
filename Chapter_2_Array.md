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
### 2.5 基础数组操作
这里有一些操纵数组的基础操作非常有用。首先就是得到数组长度的操作：
<br>
```python
print(len([1, 2, 3]) === 3);
```
重复数组操作：
<br>
```python
tempArray = [0, 1, 3] * 365
print(tempArray)
```
连接两个数组的操作：
<br>
```python
anotherTempArray = [1, 2, 3] + [4, 5, 6]
print(anotherTempArray)
anotherTempArray = [1, 2, 3] + [4, 5, 6]
```
这个操作可以将两个数组连接成一个数组。
<br>
以及，成员操作:
<br>
```python
tempArrayAgain = "butter" in ["bread", "butter", "cheese"]
print(tempArrayAgain)
```
这个操作可以检查一个特定的元素是否在某个数组中存在。
<br>
### 2.6 练习
问题：给定数组A由N个整数组成，请返回这个数组的倒序（数组A的颠倒形态）。
<br>
解答：我们可以遍历数组的前半部分，同时将前半部分的元素与后半部分数组中元素做交换。
<br>
```python
arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
def reverse(A):
    N = len(A)
    for i in range(N // 2):
        k = N - i - 1
        A[i], A[k] = A[k], A[i]
    return A

print(reverse(arr))
```
Python提供了许多内建函数和方法（以及做好的函数和方法，允许人们直接调用）。这里其实已经有一个内建函数reverse()可以解决这个练习的问题了。使用这个方法，数组A可以被轻松颠倒，就像下面这样：
<br>
```python
A.reverse()
```
