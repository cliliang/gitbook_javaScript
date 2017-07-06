##ES5学习
1、NaN是个特殊的Number值，它表示非数(Not a Number)。另一个奇特之处在于，它与自身不相等，这意味着下面的代码将返回 false：
```js
alert(NaN == NaN) //输出false
```