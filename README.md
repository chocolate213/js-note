# Java Script

27. 判断数组中是否包含重复元素(知识点：hash数组，undefined == 0)
``` javascript
var a = [1, 2, 2];

var b = [];

for(var i = 0; i < a.length; i++) {
	if(b[a[i]]) {
		console.log("有重复元素");
	} else {
		b[a[i]] = a[i];
	}
}
```

26. 去除数组中的重复元素：
``` javascript
var a = [3,3,1,2,3,4,5];

var b = [];

for(var i = 0; i < a.length; i++) {
	b[a[i]] = a[i];
}

console.log(b);

```

25. 遍历关联数组：
``` javascript
  for(var a in arrs) {
    a:数组下标
    arrs[a]：数组下标对应的值
  }
```

24. 索引数组：自动创建下标的数组都是索引数组。

23. 关联数组：JS中可以自定义数组下标，关联数组也教hash数组（通过hash函数计算数组位置），下标名字不能重复；关联（hash）数组数组是乱序的，类似于HashMap
``` javascript
var user = [];
user['name'] = 'zhangSan';
user['age'] = 20;
```

关联数组与正常数组的取值方式相同

* 注意： 关联数组中的length属性失效。

22. js中的数组
* JS中的数组角标不会越界
* 为不存在的位置的数组赋值，不会出错，将会自动创建指定下标的新元素
* 取不存在元素的下标：将会返回undefined

21. null vs undefined
undefined:是所有变量没有值的时候的默认值，自动赋值
null: 主动释放一个变量的引用

何时使用null：当使用完一个较大对象时，主动释放对象总是好的习惯

20. JS中全局函数：EcmaScript已经定义好的，开发者可以直接调用的函数称之为全局函数parseInt()等，但是alert不是（BOM）

19. 按值传递：JS中无论变量间赋值还是方法的参数传递，都是将变量中的值，复制一个副本给对方。

18. 在程序执行前或者函数被调用前，将var声明的变量和function声明的函数提前到*当前作用域*的顶部进行集中创建（仅声明提前，赋值留在原地）

17. 函数参数作为局部变量存在：

``` javascript
function m(x) {
  x = 100; //x此时是局部变量
}

function m() {
  x = 100; //x此时是全局变量
}

```

16. 函数在调用过程中，如果出现局部变量与全局变量重名，那么优先使用局部变量，如果不存在局部变量，将会使用全局变量，否则将会报错；调用结束后，所有局部变量将会被释放。（全局变量不会被销毁）

15. 函数是引用类型的对象，函数名是指向函数对象的变量；

14. JS 变量作用域

* 全局作用域：一个变量可以在程序的任意位置进行访问
* 函数作用域：一个变量只能在函数调用的时候，内部访问

* 全局变量定义在全局作用域中的变量
    * 直接在任何函数之外声明的变量，都是全局变量（全局变量都属于window对象）；
    * 无论在任何位置为从未声明过的变量赋值时，该变量将会自动创建为一个全局变量。
* 局部变量：定义在函数作用域中的变量
    * 在函数定义内部声明的变量
    * 参数变量天生就是局部变量
   
13. 隐式转换：所有算数计算均转换为number类型，所有关系运算均转换为number类型

12. js中所有表达式均返回一个结果

11. 在关系运算中（等于，不等于，大于小于），所有值都将会被转换为Number来计算，特殊情况：
* 情况一：两个字符串做比较，依次比较每一位字符的UNICode码，只要有一位字符分出大小，就停止比较，例如 "3" > "10" 将会返回true 因为3的Unicode码大于1
可以使用var n = charCodeAt(x); 获取 unicode码
* 情况二：NaN和任何数据进行大于小于等于比较均返回false；NaN和任何数据进行不等于比较均返回true，判断一个字符是否是数字使用函数isNaN()，如果是数字将返回false，否则返回true
* 情况三：undefined vs null 
undefined == null --> true
undefined === null --> false

不需要隐式转换时，需要使用三个等号来进行比较

10. 页面上获取的一切数据都是字符串类型：

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
方式一：任意类型都可以调用toString()方法转换为String类型
方式二：var str = String(x); 隐式转换

9.2.2 任意类型变为Number类型
方式一:var n = parseInt(x);从str开始读取字符串，直到碰到第一个不是数字的字符，停止读取（用于读取带单位的字符串，12px）
方式二:var n = new Number(x);  隐式转换

9.2.3 任意类型转换为Float类型
跟转换成Number类型一样var n = parseFloat(x); 但是它只认第一个小数点，例如'34.56'->35.56, 但是 '34.56.78'->34.56

9.2.4 任意类型转Boolean
var b = new Boolean(x); // 隐式转换
'' NaN undefined false 0 只有这五个数会转换为false，剩下的都是true

9.3 parseInt() vs new Number()
var n = new Number('12px') //NaN
var n = parseInt('12px')   //12

var n = new Number(true)   //1
var n = parseInt(true)     //NaN



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
