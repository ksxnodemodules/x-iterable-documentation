
# concat-iterable

 * See also:
  - [`JSIterable`](../global/readme.md#struct-jsiterable)

## Class: `ConcatIterableBase`

```
class ConcatIterableBase {
	constructor(JSIterable<any> ...);
	public JSIterator<any> [Symbol.iterator]();
	public static auto times = caller(multiply);
	public static ConcatIterable multiply(JSIterable<any>, unsigned int);
}
```

### Constructor

Constructor takes at least 1 parameters

### Function `ConcatIterableBase.times` aka `ConcatIterableBase.multiply`

```
ConcatIterable multiply(JSIterable<any> iterable, unsigned int times);
```

Create a ConcatIterable of `times` of `iterable`s

#### Examples

##### Repeat `['a', 'b', 'c']` for 5 times

```javascript
var ConcatIterable = require('x-iterable/concat-iterable');
var iterable = ConcatIterable.multiply(['a', 'b', 'c'], 5);
console.log(Array.from(iterable));
```
