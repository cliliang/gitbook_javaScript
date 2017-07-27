1、函数默认值
* 在ES6以前，是不能直接对方法传默认值的，只能用变通的方法，但ES6中，可以直接对方法函数传默认值

```js
function log(x, y = 'world'){
    console.log(x ,y);
}
log('hello')        // hello world
log('hello', 'china')//hello china
log('hello', '')    //hello
```
函数的变量是__默认声明__的，所以不能再用`let`或`const`来两次声明。
* 解构方式设置默认值

```js
function log({x, y = 5}){
    console.log(x, y);
}
log({})     //undefined, 5
log({1, 6})    //1, 6
```
* 双默认值

```js
function fetch(url, {method = 'GET'}={}){
    console.log(method);
}
fetch('http://example.com')    //GET
```
* 参数默认值的位置

通常情况下，定义了默认值的参数，应该是__函数的尾参数__。因为这样比较容易看出来，到底省略了哪些参数。如果非尾部的参数设置默认值，实际上这个参数是没法省略的。
* 函数的length属性

指定了默认值以后，函数的`length`属性，将返回没有指定默认值的参数个数。也就是说，指定了默认值后，`length`属性将失真。
```js
(function (a) {}).length // 1
(function (a = 5) {}).length // 0
(function (a, b, c = 5) {}).length // 2
```

