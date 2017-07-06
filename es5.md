##ES5学习
1、NaN是个特殊的Number值，它表示非数(Not a Number)，一般说来，这种情况发生在类型（String、Boolean 等）转换失败时。另一个奇特之处在于，它与自身不相等，这意味着下面的代码将返回 false：
```js
alert(NaN == NaN) //输出false
```
出于这个原因，不推荐使用 NaN 值本身。函数 isNaN() 会做得相当好：
```js

```