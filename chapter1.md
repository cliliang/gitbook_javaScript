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
######test() 方法
是一个正则表达式方法，方法用于检测一个字符串是否匹配某个模式，如果字符串中含有匹配的文本，则返回 true，否则返回 false。
######exec() 方法
是一个正则表达式方法，用于检索字符串中的正则表达式的匹配，该函数返回一个数组，其中存放匹配的结果。如果未找到匹配，则返回值为 null。

```
var patt = /e/;
patt.test("we are the best");
//结果为true
patt.exec("hello world");
//结果为e,因为字符串中含有e
```










