
# create-class

## Template Class: XIterable

```
template <class Super>
class XIterable : Super {
	public void forEach(JSFunction<void, void, any element, XIterable<Super> self> callback);
	public JSArray<any> map(JSFunction<any response, void, any element, XIterable<Super> self> callback);
	public bool some(JSFunction<bool stop, void, any element, XIterable<Super> self> callback);
	public bool every(JSFunction<bool next, void, any element, XIterable<Super> self> callback);
	public filter(JSFunction<bool keep, void, any element, XIterable<Super> self> callback);
	public any most(JSFunction<bool closer, void, any element, XIterable<Super> self> callback);
	public get JSNumber min, max;
}
```

### Methods: `::forEach`, `::map`, `::some`, `::every`, `::filter`

Work in the same way of `JSArray::`, but `callback` takes only 2 parameters instead of 3:
 - The first represents each element of the iterable object
 - The second represents the iterable object itself

Examples:

```javascript
var createClass = require('x-iterable/create-class');
var Iterable = createClass(Array); // Iterable is now XIterable above
var iterable = new Iterable(12, -4, 45, 6, -9); // To be continued...
```

1. Using `::forEach` to `console.log` all `iterable`'s elements

```javascript
iterable.forEach((element) => console.log(element));
```

2. Using `::map` to transform each element of `iterable` as `e` to `[e, -e, 2e]`

```javascript
console.log(iterable.map((element) => [element, -element, 2 * element]));
```
