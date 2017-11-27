### For loop
```
for (let i = 0; i < Things.length; i++) {
  Things[i]
}
```
The performance may be slow as the length property of Things will be accessed on each loop iteration.
A better way is to cache the length at initial phase, so we just access the length property once during the whole loop.
```
for (let i = 0. len = Things.length; i < len; i++) {
  Things[i]
}
```
further micro-optimization
cut the extra variable but reverse loop order
```
for (let i = Things.length; i--;) {
  Things[i]
}
```
### For-In loop
To iterates over enumerable properties of an object. Also include those enumerable properties on prototype chain.
This should not be used to iterate over an Array since the iterating order is not guaranteed.

The method **hasOwnProperty()** of Object can filter the properties on prototype chain.

