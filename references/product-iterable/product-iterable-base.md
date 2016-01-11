
# product-iterable

 * See also:
  - [`JSIterable`](../global/readme.md#struct-jsiterable)

```
class ProductIterableBase {
	public constructor(JSIterable<any> ...);
	public static auto times = caller(pow);
	public static ProductIterable pow(JSIterable<any>, unsigned int);
}
```

### Constructor

Constructor takes at least 1 parameters

### Function `ProductIterableBase.times` aka `ProductIterableBase.pow`

```
ProductIterable pow(JSIterable<any> iterable, unsigned int exponent);
```

Create a `ProductIterable` of `exponent` of `iterable`s

### Examples

#### List all arrays which contains exactly 5 elements which is `'a'`, `'b'` or `'c'`

```javascript
var ProductIterable = require('x-iterable/product-iterable');
var iterable = ProductIterable.pow('abc', 5);
console.log(Array.from(iterable));
```
