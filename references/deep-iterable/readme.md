
# deep-iterable

## Require

```javascript
var DeepIterable = require('x-iterable/deep-iterable');
```

```javascript
var DeepIterable = require('x-iterable').DeepIterable;
```

## Usage

```
class DeepIterable = XIterable<DeepIterableBase>;
```

See also:
 - [`DeepIterableBase`](./deep-iterable-base.md)

Examples:

```javascript
var DeepIterable = require('x-iterable/deep-iterable');
var target = [
	['abcdef'], 'ghi', ['jkl', ['mno'], [['pqrs', 'tuv', 'wxyz']]],
	[0, [1, 2], 3, [4, [5, 6], 7, 8]],
	new Set(Array.from('abcdefghijklmnopqrstuvwxyz').map(Symbol))
];
var iterable = new DeepIterable(target, DeepIterable.STRING_DEEPER);
console.log(Array.from(iterable));
```
