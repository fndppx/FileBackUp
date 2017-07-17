

###变量是弱类型的
	定义变量时只用 var 运算符，可以将它初始化为任意值

####关键字
	这些关键字标识了 ECMAScript 语句的开头和/或结尾。根据规定，关键字是保留的，不能用作变量名或函数名
>
break  case catch  continue  default  delete  do
else  finally  for  function  if  in  instanceof
new  return  switch  this  throw  try  typeof  var
void  while  with

#####保留字
>
abstract
boolean
byte
char
class
const
debugger
double
enum
export
extends
final
float
goto
implements
import
int
interface
long
native
package
private
protected
public
short
static
super
synchronized
throws
transient
volatile

####原始类型(基础类型)
	即 Undefined、Null、Boolean、Number 和 String。
	
####类型转换
转换成字符串 

>arrayObject.toString()  
booleanObject.toString()  
dateObject.toString()  
NumberObject.toString()  
stringObject.toString() 
 
转换成数字
>parseInt()

####闭包函数
简单的闭包实例

```
var sMessage = "hello world";

function sayHelloWorld() {
  alert(sMessage);
}

sayHelloWorld();
```
>在上面这段代码中，脚本被载入内存后，并没有为函数 sayHelloWorld() 计算变量 sMessage 的值。该函数捕获 sMessage 的值只是为了以后的使用，也就是说，解释程序知道在调用该函数时要检查 sMessage 的值。sMessage 将在函数调用 sayHelloWorld() 时（最后一行）被赋值，显示消息 "hello world"。

复杂的闭包实例

```
var iBaseNum = 10;

function addNum(iNum1, iNum2) {
  function doAdd() {
    return iNum1 + iNum2 + iBaseNum;
  }
  return doAdd();
}
```
>这里，函数 addNum() 包括函数 doAdd() （闭包）。内部函数是一个闭包，因为它将获取外部函数的参数 iNum1 和 iNum2 以及全局变量 iBaseNum 的值。 addNum() 的最后一步调用了 doAdd()，把两个参数和全局变量相加，并返回它们的和。
这里要掌握的重要概念是，doAdd() 函数根本不接受参数，它使用的值是从执行环境中获取的。
可以看到，闭包是 ECMAScript 中非常强大多用的一部分，可用于执行复杂的计算。

####对象类型


+ Object
+ Function
+ Array
+ String
+ Boolean
+ Number
+ Date
+ RegExp
+ Error
+ EvalError
+ RangeError
+ ReferenceError
+ SyntaxError
+ TypeError
+ URIError

####this
在 ECMAScript 中，要掌握的最重要的概念之一是关键字 this 的用法，它用在对象的方法中。关键字 this 总是指向调用该方法的对象

```
var oCar = new Object;
oCar.color = "red";
oCar.showColor = function() {
  alert(this.color);
};

oCar.showColor();		//输出 "red"
```

```
var oCar = new Object;
oCar.color = "red";
oCar.showColor = function() {
  alert(oCar.color);
};

oCar.showColor();		//输出 "red"
```

####prototype

+ 重命名已有方法
+ 添加与已有方法无关的方法
+ 为本地对象添加新方法
+ 重定义已有方法

####继承机制


