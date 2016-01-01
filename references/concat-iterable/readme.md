
# concat-iterable

## Require

```javascript
var ConcatIterable = require('x-iterable/concat-iterable');
```

```javascript
var ConcatIterable = require('x-iterable').ConcatIterable;
```

## Usage

```
class ConcatIterable = XIterable<ConcatIterableBase>;
```

See also:
 - [ConcatIterableBase](./concat-iterable-base.md)

Examples:

```javascript
var ConcatIterable = require('x-iterable/concat-iterable');
var array = [12, 35, -45, 8];
var string = "Hello";
var set = new Set(['a', 'b', 'c'].map(Symbol));
var concatenated = new ConcatIterable(array, string, set);
console.log(Array.from(concatenated));
```
