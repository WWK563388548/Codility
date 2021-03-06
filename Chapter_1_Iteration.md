# Chapter 1 迭代(Iterations)
<br>
&emsp;在程序开发中, 迭代意味着重复执行你的程序中的某些部分。 这一章将介绍, 允许实现迭代操作的基础程序开发结构: “for” 与 “while”循环语句。
<br>

***
### 1.1 for循环(for loops)
&emsp;如果你想重复某些操作一定次数次， 或者想要从某些集合中取出每一个元素, “for”循环绝对是个值得使用的正确工具。for循环的语法就像以下这样: 
<br>
```python
# for循环的语法
for some_variable in range_of_value:
    loop_body
```
&emsp;随着range_of_value中的每一个值被取出, 并被赋值给some_variable, for循环将重复执行loop_body中的操作。在最简单的类型中, 值的范围(range_of_value)可以是一些整数, 以 **range(最小值, 最大值 + 1)** 的形式被表示。 例如， 下面这个循环将打印0到99之间的每一个整数:
<br>
```python
# 打印0到99之间的每一个整数
for i in range(0, 100):
  print(i)
```
&emsp;从0开始遍历一组整数是非常常见的操作。（这主要是因为数组与Python语言中的list的索引都是从整数0开始的；你可以通过阅读Chapter 2数组来获取更多细节。）当我们指定一组整数时， 如果开始的值等于0的话， 那么我们就可以省略它。例如， 下面的这个循环其实与上一个例子一摸一样: 
<br>
```python
# 打印0到99之间的每一个整数(第二个版本)
for i in range(100):
  print(i)
```
***
&emsp;实例1.1.1: 我们给定一些正整数 n。让我们计算n的阶乘并将它的结果赋值给变量factorial。n的阶乘其实就是n! = 1 \* 2 \* ... \* n。我们可以从1开始乘， 直到乘遍从1到n的所有整数。
<br>
```python
# 假定n为100， 计算100的阶乘(100！)
factorial = 1
for i in range(1, 101):
    factorial *= i
print("100的阶乘: %d" % factorial)
```
**注1.1.1: 若运行该实例报错的话， 可以在程序的最上方添加 "# -\*- coding: utf-8 -\*-"这行代码。**
<br>
***
&emsp;实例1.1.2: 让我们接下来打印一个由“\*”组成的三角形， “\*”会被空格隔开。这个三角形应该有n行组成， n是一个给定的正整数， 同时连续不断的行也应该包含1, 2, 3...n个“\*”。例如， 下面将展示一个n=4的三角形: 
<br>
\*<br>
\* \*<br>
\* \* \*<br>
\* \* \* \*<br>
&emsp;我们需要用到两个for循环, 其中一个被包含在另一个for循环的内部: 外部的for循环应该运行一次就打印出一行， 而内部的for循环则每运行一次打印一个“\*”。
<br>
```python
# 打印一个n=4的三角形
for i in range(1, 5):
    for j in range(i):
        print('*', end=" ") # （, end=" "）代表print()不会自动换行, 而是会在打印“*”时, 自动在“*”后添加一个空格
    print()
```
&emsp;range()函数也可以再接收一个参数， 用来说明range（）内的迭代进程的每一步。 更正式的讲： range（start， stop， step）是一个从“start”所代表的值开始的数值序列， 连续不断的数值通过“step”所代表的值来增加或者减少， 这些数值只会小于“stop”所代表的值（对于正的“step”的值来说； 如果“step”的值是负的， 数值最终会大于“stop”所代表的值）。我们来举个例子， range（10， 0， -1）代表了序列： 10, 9, 8..., 1。需要注意的是， 当我们指定“step”后， 就不能省略“start”所代表的值了， 即使是0也不能省略。
<br>
***
&emsp;实例1.1.3: 让我们再次打印一个由n行“\*”组成的三角形， 但是这一次的三角形是对称且颠倒的。连续不断的行应该包含2n - 1, 2n - 3, ..., 3, 1个“\*”， 同时应该被0, 2, 4, ..., 2(n - 1)个空格缩进。例如， 下面这个在n=4时的三角形:
<br>
\* \* \* \* \* \* \*<br>
&emsp;\* \* \* \* \*<br>
&emsp;&emsp;\* \* \*<br>
&emsp;&emsp;&emsp;\*<br>
这个三角形应该有n行, n应该是一个给定的正整数。<br>
&emsp;这一次将会使用三个for循环： 一个在最外部, 两个在另一个for循环的内部。最外层的for循环每执行一次就会打印一行。第一个内部for循环负责打印缩进， 同时第二个内部for循环负责打印“\*”。
```python
# 在n=4时， 输出一个颠倒且对称的三角形
for i in range(4, 0, -1):
    for j in range(4 - i):
        print(" ", end=" ")
    for j in range(2 * i - 1):
        print("*", end=" ")
    print()
```
***
### 1.2. while循环(while loops)
&emsp;在无法事先判断循环所需要的次数的情况下， 我们必须使用另外一种不同的循环语句， 它被称作“while”循环。while循环的语法如下所示: 
<br>
```python
# while循环的语法
while some_condition:
    loop_body
```
&emsp;在执行循环之前, "some_condition"就已经被运算。只要“some_condition”的运算结果是true， 那么“loop_body”就会被执行。一旦“some_condition”的运算结果是false， 我们将不执行“loop_body”并退出循环。
<br>
**注1.2.1: 许多的值会被解释为false， 例如： None， 0， \[\](空的list)以及""(空的字符串)**
<br>
***
&emsp;实例1.2.1: 给定一个正整数n， 我们该如何计算n在十进制的情况下的位数（n有几位数）呢？ 第一个方法是将这个整数转换为字符串形式并计算字符的数量， 然而我们将使用另一个方法， 只使用算数运算的来解决这个问题。我们可以将这个整数不断的除以10， 然后计算除了多少次， 直到得到0为止。
<br>
```python
# 给定一个值n = 54512895662
n = 54512895662
result = 0
while n > 0:
    n = n // 10  # "//" 代表整除
    result += 1

print("n有%d位数" % result)  # 结果是n的位数是11位
```
***
&emsp;实例1.2.2: 在下面， 斐波那契数列产生了一个被反复定义的整数序列。 在斐波那契数列中，最开始的前两个数是0和1， 每一个后来的数字都是前面两个数字的和。 在这个序列中， 最开始的几个元素是： 0, 1, 1, 2, 3, 5, 8, 13。 让我们写一个程序， 它将在给定整数n的范围内， 打印出一个斐波那契数列。
<br>
&emsp;我们可以持续不断的产生和打印出斐波那契数列中的数字，直到超出n的大小为止。在每一步中， 这个程序都会只储存两个连续的斐波那契数。
<br>
```python
# 给定的整数范围是10000
n = 10000
a = 0
b = 1
while a <= n:
    print(a)
    c = a + b
    a = b
    b = c
```
***
### 1.3 遍历数值的集合
&emsp;我们已经看到了如何遍历整数。是否有可能去遍历其他类型的值呢？当然可以：我们可以使用for循环，去遍历几乎所有储存值的容器。range()函数构建了一个包含所有值的列表，甚至超过了我们应该去循环处理的。但是，我们可以传入一个通过其他方式构建的列表。
<br>
***
&emsp;实例1.3.1: 来看看这个程序：
<br>
```python
days = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday']
for day in days:
    print(day)
```
&emsp;这个程序将打印一周中的每一天。
<br>
***
&emsp;如果你遍历一个set，循环体中的程序绝对只会对set中的值执行一次；但是，执行的顺序是随机的。
<br>
&emsp;实例1.3.2: 如果我们稍微改动一下上面的程序，就像下面这样：
```python
days = set(['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday'])
for day in days:
    print(day)
```
&emsp;我们能得到以奇怪顺序排列的输出结果：
<br>
Monday<br>
Tuesday<br>
Friday<br>
Wednesday<br>
Thursday<br>
Sunday<br>
Saturday<br>
<br>
***
&emsp;遍历一个字典意味着遍历他的一组“键”（关键字）。还有就是，“键”的处理顺序也是随机的。
<br>
&emsp;实例1.3.3: 看看下面这个程序：
```python
days = {'mon': 'Monday', 'tue': 'Tuesday', 'wed': 'Wednesday', 'thu': 'Thursday', 'fri': 'Friday', 'sat': 'Saturday', 'sun': 'Sunday'}
    for day in days:
        print(day, 'stands for', days[day]) 
```
&emsp;输出结果如下: 
<br>
wed stands for Wednesday<br>
sun stands for Sunday<br>
fri stands for Friday<br>
tue stands for Tuesday<br>
mon stands for Monday<br>
thu stands for Thursday<br>
sat stands for Saturday<br>
***
