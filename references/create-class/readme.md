
# create-class

## Require

```javascript
var createClass = require('x-iterable/create-class');
```

```javascript
var createClass = require('x-iterable').createClass;
```

## Usage

### Function `createClass`

```
XIterable createClass(optional Class base = createClass.default);
```

 * Parameters:
  - `base` (optional): an [iterable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) class
 * Return value:
  - An [`XIterable<base>`](./x-iterable.md)
 * Source code:
  - https://github.com/ksxnodemodules/x-iterable/blob/v2.4.0/create-class.js#L12

Examples:

```javascript
var createClass = require('x-iterable/create-class');
var Iterable = createClass(Set);
var iterable = new Iterable([12, -5, 3, 66, 4]); // This object will be used in the following examples
```

 * Iterate `iterable`
```javascript
for (let element of iterable) console.log(element);
var double = iterable.map((element) => 2 * element);
console.log(double);
```

 * Min, max
```javascript
console.log(`${iterable.min} is the least number and ${iterable.max} is the greatest number`);
```

### Function `createClass.fromGenerator`

```
GeneratorClass createClass.fromGenerator(JSGenerator<any, GeneratorClassInstance, any ...args> generator);
```

 * Parameters:
  - `generator`: A JavaScript [generator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators) function which chooses elements for return value by `yield`ing that elements
 * Return value:
  - A [`GeneratorClass`](./generator-class.md)
 * Source code:
  - https://github.com/ksxnodemodules/x-iterable/blob/v2.4.0/create-class.js#L132

Examples:

```javascript
var Iterable = require('x-iterable/create-class').fromGenerator(mygen);
var iterable = new Iterable([-3, -2, -1, 0, 1, 2, 3], -3, -2, -1, 0, 1, 2, 3);
iterable.forEach((element) => console.log(element));
function * mygen(array, ...timeses) {
	yield * timeses.map((times) => array.map((element) => times * element));
}
```

### Class `createClass.Yield`

 * See: [Class `createClass.Yield`](./create-class-yield.md)
