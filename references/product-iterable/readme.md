
# product-iterable

## Require

```javascript
var ProductIterable = require('x-iterable/product-iterable');
```

```javascript
var ProductIterable = require('x-iterable').ProductIterable;
```

## Usage

```
class ProductIterable = XIterable<ProductIterableBase>;
```

See also:
 - [`ProductIterableBase`](./product-iterable-base.md)

Examples:

```javascript
var ProductIterable = require('x-iterable/product-iterable');
var iterable = new ProductIterable(
	[12, 4, 5, 8, -4, 3],
	[3, 8, 4, 22, -6, 5],
	[7, 2, 12, 3, 4, 22]
);
console.log(iterable.map(
	(elements) =>
		elements.reduce((prev, now) => prev * now, 1)
));
```
