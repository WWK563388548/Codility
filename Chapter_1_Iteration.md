# Chapter 1 迭代(Iterations)
<br>
在程序开发中, 迭代意味着重复执行你的程序中的某些部分。 这一章将介绍, 允许实现迭代操作的基础程序开发结构: “for” 与 “while”循环语句。
<br>

***
#### 1.1 for循环(for loops)
如果你想重复某些操作一定次数次， 或者想要从某些集合中取出每一个元素, “for”循环绝对是个值得使用的正确工具。for循环的语法就像以下这样: 
<br>
```python
# for循环的语法
for some_variable in range_of_value:
    loop_body
```
随着range_of_value中的每一个值被取出, 并被赋值给some_variable, for循环将重复执行loop_body中的操作。在最简单的类型中, 值的范围(range_of_value)可以是一些整数, 以range(最小值, 最大值 + 1)的形式被表示。 例如， 下面这个循环将打印0到99之间的每一个整数:
<br>
```python
# 打印0到99之间的每一个整数
for i in range(0, 100):
  print(i)
```
从0开始遍历一组整数是非常常见的操作。（这主要是因为数组与Python语言中的list的索引都是从整数0开始的；你可以通过阅读Chapter 2数组来获取更多细节。）当我们指定一组整数时， 如果开始的值等于0的话， 那么我们就可以省略它。例如， 下面的这个循环其实与上一个例子一摸一样: 
<br>
```python
# 打印0到99之间的每一个整数(第二个版本)
for i in range(100):
  print(i)
```
实例1.1: 我们给定一些正整数 n。让我们计算n的阶乘并将它的结果赋值给变量factorial。n的阶乘其实就是n! = 1 * 2 * ... * n。我们可以从1开始乘， 直到乘遍从1到n的所有整数。
<br>
```python
# 假定n为100， 计算100的阶乘(100！)
factorial = 1
for i in range(1, 101):
    factorial *= i
print("100的阶乘: %d" % factorial)
```
注1.1: 若运行该实例报错的话， 可以在程序的最上方添加 "# -\*- coding: utf-8 -\*-"这行代码。
<br>
