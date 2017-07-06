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
5、正则表达式，常用str的search()和replace()方法。
>/正则表达式主体/修辞符(可选)

```js
var str = "hello robot";
var n = str.search(/robot/i);
var m = str.search("robot");
结果都为6
```
正则表达式的修辞符
修辞符 | 描述 
:------ | :------: 
i | 执行对大小写不敏感的匹配 
结束
dog | bird | cat
----|------|----
foo | foo | foo
bar | bar | bar
baz | baz | baz







