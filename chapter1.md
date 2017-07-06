## 基础学习
1、===与==的[区别](http://www.runoob.com/js/js-strings.html)

2、在方法中变量如果未定义类型(var)，则变量转变为全局变量。

3、For/In循环即可以遍历对象的属性，还可以遍历数组。
遍历对象：
```js
var person={fname:"John",lname:"Doe",age:25}; 
for (x in person){
    y = y + person[x];
}
```
遍历数组：
```js
var sum = 0;
var array = [1, 3, 5];
for (i in array){
    sum += i;
}
```
4、constructor属性返回所有JavaScript变量的构造函数。
```js
"John".constructor     // 返回函数 String()  { [native code] }
(3.14).constructor     // 返回函数 Number()  { [native code] }
false.constructor      // 返回函数 Boolean() { [native code] }
[1,2,3,4].constructor     // 返回函数 Array()   { [native code] }
{name:'John', age:34}.constructor  // 返回函数 Object()  { [native code] }
new Date().constructor             // 返回函数 Date()    { [native code] }
function () {}.constructor         // 返回函数 Function(){ [native code] }
```
利用此可以查看类型，是否为数组(包含字符串 "Array")：
```js
function isArray(myArray) {
    return myArray.constructor.toString().indexOf("Array") > -1;
}
```
5、[正则表达式](http://www.runoob.com/js/js-regexp.html)，常用str的search()和replace()方法。
>/正则表达式主体/修辞符(可选)

```js
var str = "hello robot";
var n = str.search(/robot/i);
var m = str.search("robot");
结果都为6
```
正则表达式的修辞符的定义：

修辞符| 描述
------|------
i|执行对大小写不敏感的匹配
g|执行全局匹配(查找所有匹配而非在找到第一个匹配后停止)。
m|执行多行匹配。

###### test()方法
是一个正则表达式方法，方法用于检测一个字符串是否匹配某个模式，如果字符串中含有匹配的文本，则返回 true，否则返回 false。
###### exec()方法
是一个正则表达式方法，用于检索字符串中的正则表达式的匹配，该函数返回一个数组，其中存放匹配的结果。如果未找到匹配，则返回值为 null。

```
var patt = /e/;
patt.test("we are the best");
//结果为true
patt.exec("hello world");
//结果为e,因为字符串中含有e
```
6、严格模式:在严格模式下执行，消除Javascript语法的一些不合理、不严谨之处，减少一些怪异行为;
```js
"use strict"
```
- [消除代码运行的一些不安全之处，保证代码运行的安全；](http://www.runoob.com/js/js-strict.html)
- 提高编译器效率，增加运行速度；
- 为未来新版本的Javascript做好铺垫。

7、作用误区
- 在常规的比较中，数据类型是被忽略的。
```js
var x = 10;
if(x == "10") //返回true
```
但是在switch语句中，使用的却是===
```js
var y = 10;
switch(x){
     case "10": //此条并不会被执行
         break;
}
```
- 浮点型数据使用注意事项。
```js
//JavaScript 中的所有数据都是以 64 位浮点型数据(float) 来存储。
//所有的编程语言，包括 JavaScript，对浮点型数据的精确度都很难确定
var x = 0.1;
var y = 0.2;
var z = x + y;
if(z == 0.3) //返回false
```
为解决以上问题，可以用整数的除法来解决：
```js
var z = (x * 10 + y * 10) / 10;
```
- 不能在字符串中直接使用回车换行，而应该使用\
```js
var str1 = "hello
world"; //会报错
var str2 = "hello \
world";
```











