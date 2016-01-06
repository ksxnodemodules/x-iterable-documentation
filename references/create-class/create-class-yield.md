
# create-class

## Class `createClass.Yield`

 * Source code:
  - https://github.com/ksxnodemodules/x-iterable/blob/master/create-class.js#L123

```
class YieldBase {
	public constructor(Yieldable yieldable);
}
class createClass.Yield = XIterable<YieldBase>;
```

### Features

Create an [`XIterate`](./x-iterable.md) which iterate a [`Yieldable`](../global/readme.md#yieldable) object

### Examples

```javascript
var Yield = require('x-iterable/create-class').Yield;
var iterable = new Yield([-3, -2, -1, 0, 1, 2, 3]);
for (let element of iterable) {
	console.log(element);
}
```
