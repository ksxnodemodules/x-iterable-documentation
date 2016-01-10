
# parallel-iterable

## Require

```javascript
var ParallelIterable = require('x-iterable/parallel-iterable');
```

```javascript
var ParallelIterable = require('x-iterable').ParallelIterable;
```

## Usage

```
class ParallelIterable = XIterable<ParallelIterableBase>;
```

See also:
 - [`ParallelIterableBase`](./parallel-iterable-base.md)

Examples:

```javascript
var ParallelIterable = require('x-iterable/parallel-iterable');
console.log({
	'follow-the-first':
		new ParallelIterable(ParallelIterable.END_OF_FIRST, 'abcdef', 'ABCDEFGHIJKLMNOPQRSTUVWXYZ', '0123456789', 'xyz')
			.toArray(),
	'follow-the-shortest':
		new ParallelIterable(ParallelIterable.END_OF_SOME, 'abcdef', 'ABCDEFGHIJKLMNOPQRSTUVWXYZ', '0123456789', 'xyz')
			.toArray(),
	'follow-the-longest':
		new ParallelIterable(ParallelIterable.END_OF_ALL, 'abcdef', 'ABCDEFGHIJKLMNOPQRSTUVWXYZ', '0123456789', 'xyz')
			.toArray(),
	'for-count':
		new ParallelIterable(ParallelIterable.FOR_COUNT(4), 'abcdef', 'ABCDEFGHIJKLMNOPQRSTUVWXYZ', '0123456789', 'xyz')
			.toArray(),
	'just-want-to-see-why':
		new ParallelIterable(LOOKING_FOR('y'), 'abcdef', 'ABCDEFGHIJKLMNOPQRSTUVWXYZ', '0123456789', 'xyz')
			.toArray()
});
function LOOKING_FOR(value) {
	return (elements) =>
		elements.some((desc) => desc.value === value);
}
```
