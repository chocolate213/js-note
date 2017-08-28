# Java Script
9. JS数据类型转换：
9.1 隐式类型转换：JS自动完成的转换
* +运算中的隐式转换：算术计算中，一切类型都转换为number类型进行转换：比如"2" -> 2, true/false -> 0/1
* +运算中，只要有一方是字符串，两数据均转换为字符串，且+运算变为字符串连接

表达式：由数据，运算符和变量组成的一个公式，每个表达式默认从左向右，两两计算，且*每个表达式只有一个运算结果*
NaN: Not a Number: 说明运算中包含了一个无法转换为数字的类型
``` javascript
var n1 = 1, n2 = 1;
var s1 = '1', s2 = '1';
var b1 = true, b2 = false;

console.log(n1 + n2);   // 2
console.log(s1 + s2);   // '11'
console.log(s1 + n1);   // '11'
console.log(s1 - b1);   // 0    //减法不会字符串拼接，所以进行了隐式类型转换
console.log(b1 + b2);   // 1
```
9.2 强制转换：调用专门函数来完成转换
9.2.1 任意类型变为String类型
* 

方式一：任意类型都可以调用toString()方法转换为String类型
9.2.2 方式二：var str = String(x); 隐式转换

8. 字符串内容一旦创建，就不可改变。

7. JavaScrpit中，所有字符均由Unicode码表示：
``` javascript
str.charCodeAt(0);
```

6. 舍入误差：因为计算机中无法精确表示1/10，导致会产生舍入误差，不可避免。解决四舍五入：toFixed(n)函数，按照n位四舍五入;

5. JS 数据类型
5.1 原始类型：值保存在变量本地的类型：
* Number    数字
* String    字符串
* Boolean   true/flase
* undefined undefined
* null      表示不指向任何地址
4. const用来修饰常量（PI， 重力加速度g等），常量建议命名均为大写；常量无法被修改。



3. JS代码出错位置之前的代码可以正常执行，之后的代码无法执行

2. 一切变量的默认值（仅声明未赋值）为undefined

1. 声明提前：JS程序在正式执行之前，会将所有var声明的变量提前到开始位置，集中创建，但是**赋值保留在原地**(声明变量提前，赋值留在原地):

``` javascrpit
console.log(a);   //undefined
var a = 1;
console.log(a);   //1
var a = 2;
console.log(a);   //2
```

但是注意：只有war声明的变量才会提前，未声明的变量直接使用还是会报错：

``` javascript
console.log(a);   //Uncaught ReferenceError: b is not defined
a = 100;
```
