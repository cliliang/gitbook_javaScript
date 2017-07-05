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




