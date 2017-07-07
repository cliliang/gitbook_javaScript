## ES5学习

1、NaN是个特殊的Number值，它表示非数\(Not a Number\)，一般说来，这种情况发生在类型（String、Boolean 等）转换失败时。另一个奇特之处在于，它与自身不相等，这意味着下面的代码将返回 false：

```js
alert(NaN == NaN) //输出false
```

出于这个原因，不推荐使用 NaN 值本身。函数 isNaN\(\) 会做得相当好：

```js
alert(isNaN("blue"));  //输出 "true"
alert(isNaN("666"));  //输出 "false"
```

2、Object对象  
Object对象有以下几个方法：

* **hasOwnProperty\(property\)** 判断对象是否有某个特定的属性。必须用字符串指定该属性。（例如，o.hasOwnProperty\("name"\)）
* **IsPrototypeOf\(object\)** 判断该对象是否为另一个对象的原型。
* **PropertyIsEnumerable\(\)** 判断给定的属性是否可以用 for...in 语句进行枚举。
* **ToString\(\)** 返回对象的原始字符串表示。对于 Object 对象，ECMA-262 没有定义这个值，所以不同的 ECMAScript 实现具有不同的值。
* **ValueOf\(\)** 返回最适合该对象的原始值。对于许多对象，该方法返回的值都与 ToString\(\) 的返回值相同。

3、Number对象  
几个处理数值的专用方法：

* **toFixed\(\)** 方法返回的是具有指定位数小数的数字的_**字符串**_表示。例如：
  ```js
  var oNumberObject = new Number(39);
  alert(oNumberObject.toFixed(2)); //结果为"39.00"
  ```
* **toExponential\(\)** 它返回的是用科学计数法表示的数字的_**字符串形式**_。
  与 toFixed\(\) 方法相似，toExponential\(\) 方法也有一个参数，指定要输出的小数的位数。例如：
  ```js
  var oNumber = new Number(64);
  alert(oNumber.toExponential(1));//结果为"6.4e+1"
  ```

4、对象作用域  
ECMAScript中只存在一种作用域 - 公用作用域。ECMAScript中的所有对象的所有属性和方法都是公用的。因此，定义自己的类和对象时，必须格外小心。记住，所有属性和方法默认都是公用的！开发者确定了一个规约，说明哪些属性和方法应该被看做私有的。这种规约规定在属性前后加下划线：
```js
obj._color_ = "Blue";
```
5、创建对象方法
- __混合的构造函数/原型方式：__
联合使用构造函数和原型方式，就可像用其他程序设计语言一样创建对象。这种概念非常简单，即_用构造函数定义对象的所有非函数属性，用原型方式定义对象的函数属性（方法）_。结果是，所有函数都只创建一次，而每个对象都具有自己的对象属性实例。

```js
function Car(sColor, iDoor, iMpg){
  this.color = sColor;
  this.door = iDoor;
  this.mpg = iMpg;
  this.drivers = new Array("Mike", "John");
}

Car.prototype.showColor = function(){
  alert(this.color);
};
var oCar1 = new Car("red",4,23);
var oCar2 = new Car("blue",3,25);

oCar1.drivers.push("Bill");

alert(oCar1.drivers);	//输出 "Mike,John,Bill"
alert(oCar2.drivers);	//输出 "Mike,John"

```
- __动态原型方法：__
动态原型方法的基本想法与混合的构造函数/原型方式相同，即在构造函数内定义非函数属性，而函数属性则利用原型属性定义。唯一的区别是赋予对象方法的位置。

```js
function Car(sColor,iDoors,iMpg) {
  this.color = sColor;
  this.doors = iDoors;
  this.mpg = iMpg;
  this.drivers = new Array("Mike","John");
  if (typeof Car._initialized == "undefined") {
    Car.prototype.showColor = function() {
      alert(this.color);
    }; 
    Car._initialized = true;
  }
}
```


