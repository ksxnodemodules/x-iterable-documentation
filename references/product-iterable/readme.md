
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
var products = iterable.map(
	(elements) =>
		elements.reduce((prev, now) => prev * now, 1)
);
console.log(products);
```

### Tips & Tricks

#### Performance: Product of an empty iterable and a non-empty iterable

You might know what I mean after read the following; And, to be more sure, clone the code of x-iterable to test it yourself

```javascript
var ProductIterable = require('x-iterable/product-iterable');
// To be continued...
```

##### Non-empty first

```javascript
console.log(new ProductIterable('abcdef', '').toArray());
```

Returns `[]`, but according to the source code, this code would iterate for each element of `'abcdef'` &rightarrow; iterate **6 times**

##### Empty first

```javascript
console.log(new ProductIterable('', 'abcdef').toArray());
```

Returns `[]` - same as above, but according to the source code, this code iterate no charaters &rightarrow; iterate **0 times**
