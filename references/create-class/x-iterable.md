
# create-class

## Template Class: `XIterable`

```
template <class Super>
class XIterable : Super {
	public void forEach(JSFunction<void, void, any element, XIterable<Super> self> callback);
	public JSArray<any> map(JSFunction<any response, void, any element, XIterable<Super> self> callback);
	public bool some(JSFunction<bool stop, void, any element, XIterable<Super> self> callback);
	public bool every(JSFunction<bool next, void, any element, XIterable<Super> self> callback);
	public filter(JSFunction<bool keep, void, any element, XIterable<Super> self> callback);
	public any most(JSFunction<bool closer, void, any element, any old, XIterable<Super> self> callback, any init);
	public get JSNumber min, max;
}
```

### Methods: `::forEach`, `::map`, `::some`, `::every`, `::filter`, `::reduce`

Work in the same way of `JSArray::`, but `callback` takes less than `JSArray::` 1 parameter (no parameters for `index`):
 - The first represents each element of the iterable object
 - The second represents the iterable object itself

#### Examples:

```javascript
var createClass = require('x-iterable/create-class');
var Iterable = createClass(Int32Array); // Iterable is now XIterable above
var iterable = new Iterable([12, -4, 45, 6, -9]); // To be continued...
```

##### Using `::forEach` to `console.log` all `iterable`'s elements

```javascript
iterable.forEach((element) => console.log(element));
```

##### Using `::map` to transform each element of `iterable` as `e` to `[e, -e, 2e]`

```javascript
console.log(iterable.map((element) => [element, -element, 2 * element]));
```

##### Using `::reduce` to calculate summation of a sequence

```javascript
console.log(iterable.reduce((prev, now) => prev + now, 0));
```

### Method: `::most`

Find extremum of an iterable e.g. minimum, maximum

This method takes 2 arguments:
 - `callback` is a function
 - `init` is a value of any kind which should not be the extremum

Function `callback` takes 3 arguments:
 - `element`: current element
 - `old`: old extremum
 - `self`: the iterable object

If `callback(element, old, self)` returns `true`, `element` will be assigned to `old` for the next element

#### Examples

```javascript
var createClass = require('x-iterable/create-class');
var Iterable = createClass(Array);
```

##### Using `::most` to find longest string

```javascript
var iterable = new Iterable('abcdef', 'Hello, World!!', '12', 'alphabet');
var longest = iterable.most((element, longest) => element.length > longest.length, '');
console.log(`The longest string is: "${longest}"`);
```

##### Using `::most` to find shortest array/string

```javascript
var iterable = new Iterable('abcdefghijklmnopqrstuvwxyz', [0, 1, 2, 3], Array.from('Hello, World!!'));
var shortest = iterable.most((element, shortest) => element.length < shortest.length, {length: Infinity});
console.log({result: shortest});
```
