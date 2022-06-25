# 1.JS代码的三种写入方法

## 1.1js代码写在HTML中

```html javascript
<input type="button" value="按钮" onclick="alert(123)">
```

onclick="alert(123)"使点击按钮后弹出内容是123窗口

## 1.2js代码写在HTML的script标签中

```HTML JS
<script type="text/javascript">
	alert(345)
</script>
```

## 1.3js代码写在js文件中

```HTML JS
<script type="text/javascript" src="./JS课程1.js">
    
</script>
```

src="./JS课程1.js"将JS文件和HTML文件连接

# 2.变量

## 2.1基本概念

声明一个变量，变量是一个容器

```js
var aa（变量名）;
```



给变量赋值

```
aa = 18;
```



声明一个变量并给变量赋值

```js
var	age(变量名) = 18;
```



一次性声明多个变量并赋值

```js
var h1 = 1, h2 = 2, h3 = 3;
```

变量的命名必须是用数字,字母,下划线_和$符号       变量名不能用数字开头       变量名不能是关键字



变量区分大小写

```js
var number = 1;
var Number = 2;
```



多行相同变量赋值后面的值会覆盖前面的值

```js
var number = 1;
var number = 2;
```

变量的命名最好使用驼峰命名



将两个变量之间的值进行交换

```
var a = 1;
var b = 2;
var c = a;
a = b;
b = c;
```

# 3.数据类型

## 3.1概要

数据类型：数值型number、字符串型string、布尔Boolean、undefined、null、对象object

使用单引号或双引号 引起来的数据都是字符串

```js
var str1 = 李四;		这不是字符串型
var str2 = '李四';	加上引号是字符串型
```

如果要在字符串中要使用引号，要加转义字符\ 转义字符加在引号前

\n 换行，\t 制表，\b 空格，\r 回车，

```js
var str3 = '\'李四\'';
```



```js
var s1 = '123';
s1.length			计算s1的长度
var s2 = '456';
var s3 = s1+s2;		字符串的拼接
```

+号有时代表数学运算有时代表字符串的拼接   从前往后进行计算如果两个变量都是数值+号进行数学计算，直到遇到第一个字符串型，之后所有的+号都是字符串的拼接



Boolean代表逻辑型只有true和false两个值，区分大小写，计算机内部储存true为1、false为0

undefined代表一个声明了没有赋值的变量，变量只声明时默认时undefined

null表示空，变量的值要为null要手动设置



```js
/* 
	多行注释
*/
```



## 3.2其他类型转为字符串型

```js
var n =5;
var s = n.toString();		String的S要大写
var s = String(n);
var s = ''+ n;
console.log(typeof s);		在浏览器的控制台中显示是什么类型
```



## 3.3其他类型转为数值型

```js
var a = '1';
var b = Number(a);				null会转为0
var c = parseInt('2');			只能将只有数字的值转为数值型，不可以是小数，I要大写
var d = parseFloat('1.23');		字符串的开头是数字的话将后面跟着的正常数据转为数值型，可以是小数,F要大写
null和undefined用parseInt和parseFloat转换不了
```



## 3.4其他类型转为Boolean

```js
var a = Boolean('0')		字符串内有内容转为逻辑型就是true
var b = Boolean('')			字符串内没有内容转为逻辑型是false
var c = Boolean(0)			数值型中0转换为逻辑型是false其他数字是true
var d = Boolean(null)		null转换为逻辑型是false
var e = Boolean(undefined)	nudefind转换为逻辑型是false
```



# 4.运算符

## 4.1一元运算符

（++  -- 对自身操作+1或者-1） %是取余数

```js
var n = 5;
n++		++n
n--		--n
操作符在变量前后都可以进行自身运算
操作符在变量前面，先进行自身运算，再进行其他运算
操作符在变量后面，先进行其他运算，再进行自身运算
var a = 1;
var b = a++ + ++a;		b = 1+3
a=3，b=4
var a = 1;
var b = a++ + ++a;		b = 2+2
a=3,b=4
var a = 1;
var b = ++a + ++a;
a=3，b=5
```



## 4.2逻辑运算符

```
&& 逻辑与运算符
|| 逻辑或运算符
!  逻辑非运算符
&&的优先级＞||的优先级
js中逻辑运算的结果是决定整个表达式的子表达式的值
```



## 4.3比较运算符

```
==	判断左右两边是否相等，只比较值不比较数据类型
!=	不等
===	全等比较，既比较值又比较数据类型
!==	不全等
```



## 4.4赋值运算符

```
=	赋值
+=	变量自身加数据		a=a+1等于a+=1
-=	同理
/=	同理
*=	同理
%=	同理
```



## 4.5运算符的优先级

```
1.()
2.一元运算符 ++--！
3.算数运算符 */%+-
4.关系运算符 >< >= <=
5.比较运算符 == === ！= !==
6.逻辑运算符 && ||
7.赋值运算符 =
```



# 5.流程控制

## 5.1分支结构

### if判断

```js
if(条件){执行代码}
else if(条件){执行代码}
else(条件){执行代码}
```



### switch-case的用法

```js
switch(值){
	case 值1:
		代码
		break;
	case 值2:
		代码
		break;
	default:
		代码
		break;
}
break表示跳过
switch内的值和case内的值进行比较是否相等，相等则运行代码，不相等与下一个case内的值进行比较，都不相等则运行default内的代码
```



## 5.2循环结构

### while循环

```js
while(条件){代码}
先判断条件是否成立再执行代码
```

### do while循环

```js
do(代码)while{条件}
先执行代码再判断条件是否成立
```

### for循环

```js
for(初始表达式;判断表达式;自增自减运算){代码}
示例:
for(var i=1;i<10;i++){
	console.log(i);
}
```

break 表示跳出循环（循环结束）

continue 表示跳出当前循环继续下一个循环（循环未结束）

```js
找出10以内不能被2整除的数
for(var i=1;i<10;i++){
	if(i%2 == 0){
		continue
	}
	console.log(i)
}
找出10以内第一个被2整除的数
for(var i=1;i<10;i++){
	if(i%2 == 0){
		console.log(i)
		break
	}
}
```

# 6.数组

## 6.1数组的创建

```js
var z = ['a','b','c'];
var y = [1，2，3]；
数组内的数据顺序从0开始
```

