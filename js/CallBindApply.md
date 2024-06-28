## call、apply、bind

call、apply、bind 作用是改变函数执行时的上下文，简而言之就是改变函数运行时的 this 指向

```js
var name = 'lucy'
var obj = {
  name: 'martin',
  say: function () {
    console.log(this.name)
  }
}
obj.say() // martin，this 指向 obj 对象
setTimeout(obj.say, 0) // lucy，this 指向 window 对象
```

## call 用法

call 方法调用一个函数，并使用指定的 this 值和单独给出的参数来调用该函数。

```js
/***
 * @param thisArg 参数一传入this指向
 * @param argArray  参数二传入参数 1,2,3 可选
 * @returns {*} 直接返回函数执行结果(调用函数)
 */

var obj = {
  name: 'martin',
  say: function () {
    console.log(this, 'this')
    console.log(this.name)
  }
}

var obj1 = { name: 'lucy' }

obj.say() // 输出martin this指向是obj对象
obj.say.call(obj1) // 输出lucy 改变this指向到obj1对象
```

> call 传参

```js
function Product(name, price) {
  this.name = name
  this.price = price
}
// call 传参方式 ...args[]
function Food(name, price) {
  Product.call(this, name, price)
  this.category = 'food'
}

function Ship(...args) {
  Product.call(this, ...args)
  this.category = 'Ship'
}

function Car() {
  //  Array.prototype.slice.call
  // Array.prototype.slice.call(arguments)能将具有length属性的对象(key值为数字)转成数组。[]是Array的示例，所以可以直接使用[].slice（）方法。
  const args = Array.prototype.slice.call(arguments)
  //或者 const args = [].slice.call(arguments)
  Product.call(this, ...args)
  this.category = 'Car'
}

console.log(new Food('cheese', 5))
console.log(new Food('和谐号', 50000))
console.log(new Car('宝马', 50000, 50000))
```
