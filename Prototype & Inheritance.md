### Prototype

#### object prototype and prototype chain

Every object in Javascript has a prototype. And the prototype also is an object.

So we can get a prototype chain and the end of the chain links to **Object.prototype** whose prototype is null.

When trying to access a property of an object, will firstly find in object self. If cannot find it, will look up its prototype, and so on until find the property or the end of the prototype chain is reached.

#### function property 'prototype'

But what is "Object.prototype"? It's quite different from the object prototype we mentioned above.

Every function in Javascript has a property named 'prototype'. And this property ia an object.
When the function called as a constructor(use 'new'), the function property 'prototype' will be assigned as the prototype of the instance created by the constructor
Function's prototype has a property named 'constructor' which point to the function self.

#### __proto__

The prototype can be accessed by __proto__ property, but it's not a standard property and depends on browsers' implement

```js
// Equal to: var obj = new Object({ a: 'a' })
var obj = { a: 'a' };
console.log(obj.__proto__ === Object.prototype);  // true
console.log(Object.prototype.constructor === Object);  // true

// Equal to: var obj = new Array(1, 2)
var arr = [1, 2];
console.log(arr.__proto__ === Array.prototype);  // true
console.log(Array.prototype.__proto__ === Object.prototype);  // true
console.log(Array.prototype.constructor === Array);  // true
```





