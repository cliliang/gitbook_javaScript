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
同样，rest参数也不记入`length`属性
```js
(function(...args){}).length //0
```
2、作用域
一个需要注意的地方是，如果参数默认值是一个变量，则该变量所处的作用域，与其他变量的作用域规则是一样的，即先是当前函数的作用域，然后才是全局作用域。
```js
let foo = 'out';
function bar1(fun = x => foo){
    let foo = 'in';
    console.log(fun());
}
bar1(); //out

function bar2(fun = x => foo){
    let foo = 'in';
    console.log(fun());
}
bar2(); //Error 匿名函数里面的foo指向函数外层，
        //但是函数外层并没有声明foo，所以就报错了。
```
3、rest参数，解构赋值

```js
function push(array, ...args){
    args.forEach(function(item){
        array.push(item);
    });
}
let a = [];
push(1, 3, 6);
```
4、扩展运算符
扩展运算符是三个点（...）。它好比rest参数的逆运算，将一个数组转为用逗号分隔的参数序列。该运算符主要用于函数调用。
```js
function add(x, y){
    return x + y;
}
var items = [3, 6];
add(...items); // 9
```
5、name属性
如果将一个匿名函数赋值给一个变量，ES5的name属性，会返回空字符串，而ES6的name属性会返回实际的函数名。

```js
const foo = function(){};
foo.name(); //foo
```
如果将一个具名函数赋值给一个变量，则ES5和ES6的name属性都返回这个具名函数原本的名字。
```js
const foo1 = function faz(){};
foo1.name(); // faz
```
6、箭头函数(=>)
由于大括号被解释为代码块，所以如果箭头函数直接返回一个对象，必须在对象外面加上括号。
```js
var getTempItem = id => ({ id: id, name: "Temp" });
```
7、函数绑定
函数绑定运算符是并排的两个双冒号（::），双冒号左边是一个对象，右边是一个函数。该运算符会自动将左边的对象，作为上下文环境（即this对象），绑定到右边的函数上面。由于双冒号运算符返回的还是原对象，因此可以采用链式写法。



