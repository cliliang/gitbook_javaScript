1、属性的简洁写法
ES6允许在对象上只定义属性名，没有属性值。这时，属性值就等于属性名所对应的变量。
```js
var fun = function(x, y){
    return {x,y};
}
```
