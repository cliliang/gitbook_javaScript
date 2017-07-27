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
